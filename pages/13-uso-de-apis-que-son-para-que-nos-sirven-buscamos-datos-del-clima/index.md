<!--
.. title: 13- Uso de APIs. Qué son, para qué nos sirven.
.. slug: 13-uso-de-apis-que-son-para-que-nos-sirven-buscamos-datos-del-clima
.. date: 2020-11-26 18:08:42 UTC-03:00
.. tags: 
.. category: 
.. link: 
.. description: 
.. type: text
-->


# Unidad 13

## Uso de APIs. Qué son, para qué nos sirven. Buscamos datos del clima.

### ¿Qué es una API?

API significa Application Programming Interface, y en español eso significa Interfaz de Programación de Aplicaciones.  
Las API es la forma en que se interconectan y comunican dos programas diferentes.

### REST: Representational State Transfer

REST es el protocolo de configuración de APIs más utilizado hoy en día. Está basado en el protocolo HTTP de Internet, y utiliza sus verbos y recursos para configurar las acciones de una API.

Veamos esto con un ejemplo:

```
GET www.google.com
```

Esta llamada HTTP ejecuta el verbo `GET`, llamando al recurso o endpoint `www.google.com`, y obtendrá como respuesta lo que envíe de retorno el servidor.

Existen varios verbos diferentes, siendo los más utilizados: **POST**, **GET**, **PUT** y **DELETE**.

GET se utiliza para consultar información.
POST y PUT sirven para enviar información al servidor para ser procesada.
DELETE se utiliza para ejecutar tareas de eliminación en el servidor.

## Ejercitación

### Usemos una API, consultar datos del clima.

1- Vamos a crear una cuenta en el sitio http://openweathermap.org/.

2- Luego, debemos confirmar nuestro email cuando el sitio nos lo solicite. Deberíamos recibir por email la API Key a utilizar en nuestro programa.

3- De no recibirla, podemos encontrarla en el panel de control de nuestra cuenta dentro del sitio.

4- Copiamos el siguiente código en un programa nuevo, y reemplazamos nuestra API Key.

``` python
import requests
import builtins

parametros = {
    'appid': '<Reemplazar por nuestra API Key>',
    'lang': 'es',
    'units': 'metric'
}

def buscarClima(ciudad):
    parametros['q'] = ciudad
    r = requests.get("http://api.openweathermap.org/data/2.5/weather", params=parametros)
    if r.status_code == requests.codes.ok:
        clima = r.json()
        # print(clima)
        print("Información para " + clima['name'] + ", " + clima['sys']['country'])
        print("Estado: " + clima['weather'][0]['description'])
        print("Temperatura: ", str(round(clima['main']['temp'])), "°C")
    else:
        print("Hubo un error:")
        if r.status_code == requests.codes.not_found:
            print("No se encuentra ese lugar")
        print(r)

if __name__ == "__main__":
    lugar = input("Ingrese una ciudad: ")
    buscarClima(lugar)

```