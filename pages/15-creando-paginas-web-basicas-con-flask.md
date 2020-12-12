<!--
.. title: 15- Creando páginas web básicas con Flask
.. slug: 15-creando-paginas-web-basicas-con-flask
.. date: 2020-12-10 17:51:20 UTC-03:00
.. tags: 
.. category: 
.. link: 
.. description: 
.. type: text
-->

# Unidad 15

## Creando páginas web básicas con Flask

Flask es un framework en Python usado para crear sitios web. Es muy configurable, y muy extensible. Hay muchos otros proyectos que conectan diferentes tipos de aplicaciones, bases de datos, utilizades, etc. con Flask.

### Instalación

Lo primero que debemos hacer como en cualquier nuevo proyecto en Python, es crear un nuevo entorno virtual. Una vez activado, debemos instalar Flask.

```
python -m venv venv
.\venv\Scripts\activate
(venv) c:\...\> pip install flask
```

Luego creamos un archivo python donde escribir nuestro código: `sitioweb.py`.

### Aplicación inicial: Hola Mundo!

Incluimos este código en el archivo python:

``` python 
from flask import Flask

app = Flask(__name__)

@app.route('/')
def hola():
    return 'Hola, Mundo!'

```

Para ejecutarlo, debemos escribir lo siguiente en la terminal:

```
set FLASK_APP=sitioweb.py
flask run
```

### Página web usando una plantilla

Agreguemos ahora esta nueva función:

``` python 
@app.route('/')
def saludo():
    return '''
<!doctype html>
<title>Hola, como estas?</title>
  <h1>Bienvenido a tu nuevo sitio web!</h1>
'''
```

Con Ctrl+C detenemos la ejecución de Flask si ya estaba corriendo. Con `flask run` nuevamente lo ejecutamos.

### Plantilla en un archivo template

Creamos una carpeta `templates`, y dentro de ella un archivo `saludo.html` con el siguiente contenido:

``` html
<!doctype html>
<title>Hola, como estas?</title>
{% if name %}
  <h1>Hola {{ name }}!</h1>
{% else %}
  <h1>Hola, Mundo!</h1>
{% endif %}
```

Y agregamos esta función:

``` python
@app.route('/saludo/<name>')
def saludo(name=None):
    return render_template('saludo.html', name=name)
```
