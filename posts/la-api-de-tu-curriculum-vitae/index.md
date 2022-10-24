<!--
.. title: La API de tu currículum vitae
.. slug: la-api-de-tu-curriculum-vitae
.. date: 2020-11-16 16:05:51 UTC-03:00
.. tags: tutorial,python,api,flask,github,heroku
.. category: Tutorial
.. link: 
.. description: Cómo crear una API para que sea tu currículum
.. type: text
-->

# La API de tu currículum vitae
## Cómo crear una API para que sea tu currículum

En este post vamos a escribir nuestra propia API mediante Flask, usando como datos nuestro currículum vitae. Luego vamos a publicar el código en GitHub y finalmente usando Heroku la implementaremos online. Al final tendrás tu propia API funcionando.


1- Instalar Python.  

En [la página oficial de Python](https://www.python.org/downloads/) podrás encontrar la versión de Python para tu sistema operativo.

2- Crear un Virtual Environment.  

En Python, la mejor forma de aislar un proyecto y sus dependencias es con un entorno virtual. Es una carpeta especial donde se instalará todo lo que tu proyecto necesita.  
Creamos una nueva carpeta donde guardar nuestro proyecto `mkdir cv-nahuel-api`, y cambiamos a esta `cd cv-nahuel-api`.
Creamos un entorno virtual con el comando: `python -m venv virtenv`.

3- Instalamos lo necesario.  

Primero que nada, debemos activar nuestro entorno virtual, para que el sistema sepa que queremos usar esos programas de esta carpeta en particular.  
Ejecutamos `source virtenv/Scripts/activate`. Ahora, los comandos `python` y `pip` que ejecutemos serán los de la carpeta `virtenv`.
Instalamos Flask, que por el momento será nuestra única dependencia y herramienta que utilizaremos para construir nuestra API: `pip install flask`. Junto con él, se instalan sus propias dependencias: Jinja2, Werkzeug y otros.

4- Creamos nuestra API.  

En la carpeta principal de nuestro proyecto, creamos el archivo api.py con el siguiente esqueleto:
``` python
#!flask/bin/python
# -*- coding: UTF-8 -*-

from flask import Flask, request

app = Flask(__name__)


if __name__ == '__main__':
    app.run(debug=True)
```

Bien, nuestra api ya la podemos ejecutar con `python api.py`, pero aun no hace nada.
Vamos a agregar la ruta básica, '/', para que muestre algo de información cuando la ejecutamos. Este código debe ir debajo de la definición de la variable `app`, pero antes del `if` del final.

```python
@app.route('/')
def index():
    info = {
        "mensaje" : "Bienvenido a la API del curriculum vitae de Nahuel Tori.",
        "acciones" : [
            "GET /curriculum",
            "POST /mensajes"
        ]
    }
    return jsonify(info)

```
También debemos agregar `jsonify` al import inicial. ¿Qué hace esta función? Crea un objeto de tipo diccionario, con la información que queremos que nuestro servicio retorne. En la última línea, nos ayudamos del método `jsonify` de Flask para transformar ese objeto en un texto JSON válido.  
Podemos ver agregamos una anotación al inicio `@app.route`, que usamos para indicarle a Flask cuál es la ruta que debe resolver con esta función.

Ahora si, cuando ejecutamos nuestra API y accedemos en nuestro navegador a `http://127.0.0.1:5000/`, podremos ver el mensaje.

Si no habías detenido previamente la ejecución, podrás ver cómo Flask detecta el cambio en el archivo al ser guardado, y vuelve a recargar la API.

5- Agregamos más recursos y acciones

Como buena API, en la nuestra los nombres de los endpoints describen los recursos usando sustantivos, y los verbos del protocolo HTTP describen las acciones que se pueden realizar.  
Vamos a crear un recurso `curriculum`, que nos permita devolver la información de nuestro perfil personal mediante el verbo GET. También vamos a crear un recurso `mensajes`, donde usando el verbo POST nuestra API pueda recibir mensajes de quienes quieran ponerse en contacto con nosotros.

``` python
@app.route('/curriculum', methods=['GET'])
def cv():
    url_imagen = request.host_url + "static/FotoNahuel.jpg"
    cv = {
        "nombre" : "Nahuel",
        "apellido" : "Tori",
        "residencia" : "Argentina",
        "experiencia" : [{
            "posicion" : "< describe tu posición>",
            "empresa" : "< nombre de tu empresa >",
            "desde" : "< cuándo empezaste a trabajar >",
            "hasta" : "< si ya no trabajas más, cuándo >",
            "descripcion" : "< detalles >"
        }],
        "educación" : {
            "nivel" : "< nivel de tus estudios >",
            "titulo" : "< nombre de tu carrera >",
            "institucion" : "< dónde estudiaste >",
            "facultad" : "< más detalles >"
        },
        "intereses" : ["python", "apis", "enseñar"],
        "redes" : {
            "github" : "https://github.com/nahueltori",
            "twitter" : "https://twitter.com/nahueltori",
            "linkedin" : "https://www.linkedin.com/in/nahueltori"
        },
        "foto" : url_imagen
    }
    return jsonify(cv)

```
En esta función, estamos generando un gran objeto diccionario con toda nuestra información. Estos son algunos campos propuestos; vos podés incluir los que te parezcan mejor, como en tu CV.  
En la primera línea describimos el endpoint dentro de la anotación, y también aclaramos que específicamente se responderá sólo al verbo GET.  
Dentro de la función, lo primero que hacemos es armar la URL completa para proporcionar también una imagen nuestra: la imagen debemos guardarla dentro de una nueva carpeta llamada `static` dentro de nuestro proyecto. Recuerden agregar `request` al import de Flask en la primera línea.

Luego de probar su nuevo endpoint, probablemente varios caracteres no se lean correctamente. En realidad, es el formato estándar Unicode en los archivos JSON, y las computadoras pueden leerlo sin problemas. Para que nosotros también podamos, hay que agregar esta línea luego de definir la variable `app`:  
`app.config['JSON_AS_ASCII'] = False`

Agregamos el otro endpoint:
```python
@app.route('/mensajes', methods=['POST'])
def contacto():
    mensaje = request.get_data()
    if not mensaje:
        abort(400, description="Debe enviar su mensaje en el body del POST.")
    print("MENSAJE DE CONTACTO: " + str(mensaje))
    return "Gracias por su mensaje."
```

En esta función, definimos nuestro endpoint `mensajes` aceptando solamente llamadas mediante el verbo POST.  
Lo que hacemos es buscar el mensaje en el cuerpo del llamado HTTP: si no hay nada, entonces respondemos con un error de código 400, que significa que el request recibido no tiene el formato correcto. También indicamos en la descripción qué es lo que está mal: de esta forma, quien nos invoque sabrá cómo hacerlo correctamente la próxima vez. También necesitaremos agregar `abort` entre los imports de Flask.  
Si había algún contenido en el cuerpo del llamado, entonces ese es el texto que nos interesa: nuestro mensaje. En este ejemplo, por simplicidad solamente hacemos un `print` de su contenido, pero podría agregarse el código para mandar este mensaje por email, por ejemplo. Finalmente, devolvemos un mensaje de respuesta ante una llamada correcta.


Muy bien, en este punto, nuestra API está conceptualmente terminada. Pueden extenderla todo lo que gusten, agregar más endpoints, validaciones, información, links o lo que gusten.

6- Preparamos para subir nuestra API a un servicio de Host

En primer lugar, debemos agregar esta línea de código:

```python 
app.config['JSONIFY_PRETTYPRINT_REGULAR'] = True
```

Y cambiar esta:
```python 
if __name__ == '__main__':
    app.run()
```
Verán que al no estar utilizando más el modo debug, no funciona más el hot-reloading. Tampoco se formatea el mensaje JSON para verse mejor, por eso la primera configuración.

Luego, debemos crear tres archivos de configuración necesarios para el repositorio online y para subir y ejecutar correctamente el proyecto en nuestro Host.

### .gitignore
En la carpeta principal, creamos un archivo llamado `.gitignore`. se utiliza para excluír determinados elementos de que sean guardados en nuestro repositorio de código en GitHub, que haremos en el siguiente paso.
El archivo debe contener las siguientes líneas:
```
__pycache__/
.env
virtenv/
```
Principalmente, nos servirá para que toda la carpeta de nuestro entorno virtual local no sea sincronizada, ya que no es necesario.

### requirements.txt
También lo creamos en la carpeta principal, y debe tener el siguiente contenido:
```
Flask
gunicorn
```
Este archivo indica qué dependencias tiene nuestro proyecto, y que serán instaladas cuando se quiera ejecutar. Pueden ver que hay una nueva que no nombramos antes, `gunicorn`. Esta la utilizaremos para correr nuestro servidor web de manera productiva, ya que el que Flask provee solamente sirve para hacerlo de forma local o en ambientes de desarrollo.

### Procfile
En la carpeta principal creamos un archivo llamado `Procfile`, con el siguiente contenido:
```
web: gunicorn api:app
```
Este archivo será utilizado por Heroku, nuestro Host online, para ejecutar la api.

7- Sincronizamos nuestro código en GitHub

GitHub es el repositorio online más popular donde subir nuestro código, y es muy utilizado por reclutadores para conocernos más a través de cómo programamos.  
Para poder subir nuestro código a GitHub, antes debemos tener instalado algún cliente Git. Para eso, lo podemos descargar [acá](https://git-scm.com/download).  
[Acá](https://training.github.com/downloads/es_ES/github-git-cheat-sheet/) hay una guía rápida sobre cómo configurar la herramienta para usarla por primera vez.

Vamos ahora a GitHub, y si aun no tienen una cuenta les recomiendo crearla: la pueden poner en la información de su currículum en la API :). Luego de crear la cuenta, vamos a [new](https://github.com/new) a crear el repositorio para guardar nuestro proyecto.  
Completar con un nombre relacionado al proyecto, como `cv-nahuel-api` por ejemplo. **Muy importante:** no tildar ninguna de las opciones de inicialización del repositorio en *Initialize this repository with*. Eso nos permitirá subir todo el código de nuestra carpeta local sin problemas.

Una vez creado el repositorio, podemos subir el código siguiendo las mismas instrucciones que vemos en pantalla:

* Parados en la carpeta de nuestro proyecto, ejecutamos `git init`.
* Luego `git add .` para incluir todos los archivos del directorio.
* Con `git commit -m "Primera versión de nuestro CV en una API"` generamos el paquete de código trabajado.
* Creamos un nombre para la línea por defecto donde subir el código: `git branch -M main`.
* Configuramos nuestra carpeta con el repositorio online creado: `git remote add origin https://github.com/nahueltori/cv-nahuel-api.git`
* Finalmente, con este comando nuestro código quedará guardado en la nube: `git push -u origin main`.

En adelante, cada vez que hagamos un cambio, sólo tendremos que ejecutar lo siguiente:

* Luego `git add .` para incluir todos los archivos del directorio.
* Con `git commit -m "Comentario descriptivo de lo que hicimos"` generamos el paquete de código trabajado.
* Finalmente, con este comando nuestro código quedará guardado en la nube: `git push -u origin main`.


8- Heroku: hosting de proyectos para desarrolladores

Heroku es una plataforma cloud que nos permite crear aplicaciones muy rápidamente, sólo ponemos el código y la plataforma se encarga de toda la infraestructura para que esté funcionando.

* Si aun no tienen una cuenta, vamos a crear una nueva.
* En el dashboard, hacemos click en "New" -> "App".
* En Deployment method, seleccionamos "GitHub". Si nunca habían conectado su cuenta previamente, los redirigirá al sitio de GitHub donde deberán ingresar su usuario y contraseña para autorizar a Heroku poder buscar su código.
* Una vez conectadas las cuentas, podrán buscar el repositorio por su nombre: `cv-nahuel-api` y apretan "Search".
* En el listado les muestra los repositorios encontrados, simplemente clickeamos "Connect" en el correcto.
* Es una muy buena idea activar los Deploys automáticos: cada vez que hagan push en su repositorio, Heroku se dará cuenta e instalará la nueva versión de su aplicación. **Importante:** si lo activamos, recordar sólo hacer push del código luego de haber probado que nuestra aplicación funciona correctamente.
* Finalmente, debemos hacer el primer deploy de nuestra aplicación. Para eso, clickeamos el botón "Deploy Branch" en la sección "Manual deploy".

Si todo funcionó bien, Heroku se tomará un tiempo para hacer todo lo necesario y entregarles una aplicación instalada. Pueden verla con el botón "Open app".
Si algo funcionó mal, en el botón "More" pueden ir a "View logs" y chequear qué funcionó mal.

En este momento, pueden probar agregar algo a su proyecto (por ejemplo el README.md, o algún nuevo endpoint), hacer el push en el repositorio de GitHub y ver cómo Heroku instala automáticamente la nueva versión de su aplicación.

Espero que te haya servido, y si te quedó alguna pregunta o algo no te funciona, no dudes en escribirme.

