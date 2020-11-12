<!--
.. title: 11. Manejo de archivos de texto.
.. slug: 11-manejo-de-archivos-de-texto
.. date: 2020-11-12 17:07:08 UTC-03:00
.. tags: 
.. category: 
.. link: 
.. description: 
.. type: text
-->

# Unidad 11

## Manejo de archivos de texto

El manejo de archivos es una parte importante en la programación, ya que nos permiten almacenar información. Pueden venir en formato de base de datos, de mensaje de otra aplicación, de tabla, CSV, imágenes, o simplemente un archivo de texto plano. Todos pueden ser utilizados a través de nuestros programas en Python.

### Leer un archivo

Con la sentencia `with open` abrimos un archivo para procesarlo de alguna manera. En este caso para leerlo completamente:

``` python
with open("demofile.txt", "r") as f:
    archivo_completo = f.read()
print(archivo_completo)
```

En este caso, leemos las líneas de a una. Una línea termina cuando se encuentra el caracter de nueva línea (\n):

``` python
with open("demofile.txt", "r") as f:
    linea = f.readline()
    otra_linea = f.readline()
```

Otra forma de leer todas las líneas de un archivo:

``` python
with open("demofile.txt", "r") as f:
    for line in f:
        print(line)
```

### Escribir en un archivo

Utilizando el parámetro 'a' luego del nombre del archivo al abrirlo, vamos a estar agregando datos al final de éste:

``` python
with open("demofile.txt", "a") as f:
    f.write("Datos adicionales" + '\n')
    f.write("Al final del archivo")
```

Si abrimos el archivo con el parámetro 'w', vamos a estar reemplazando todo su contenido:

``` python
datos = {"a": 1, "b": 2, "c": 3}
with open("demo.txt", "w") as f:
    for elemento in datos:
        f.write(elemento + ':' + str(datos[elemento]) + '\n')
```

### Ejercicios:

1. Tomando como punto de partida el programa de la unidad 10, vamos a agregarle la funcionalidad mediante la cual la información se guarde en un archivo. De este modo, una vez terminado el programa podremos recuperarla nuevamente. Para esto, hay que agregar la lectura del archivo apenas comienza el programa, y el guardado de la información antes de terminarlo.

    *Ayuda 1:* Antes del bucle principal del programa, es un buen momento para leer algún archivo predeterminado donde almacenemos la información del programa. Es importante conocer el nombre y formato de la información dentro del archivo, por lo que puede ser útil primero hacer la otra parte.

    *Ayuda 2:* Luego de que se haya terminado el bucle principal, el programa va a terminar. Este es un buen punto para invocar la funcionalidad de guardado de la información. Elegir un nombre para el archivo, y poner atención en el formato en que se guardará la información del diccionario.
