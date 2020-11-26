<!--
.. title: 12- Librerías externas e internas: import
.. slug: 12-librerias-externas-e-internas-import
.. date: 2020-11-26 18:08:21 UTC-03:00
.. tags: 
.. category: 
.. link: 
.. description: 
.. type: text
-->

# Unidad 12

## Librerías externas e internas: import

En Python, tenemos dos conceptos para separar el código en diferentes secciones: Módulos y Paquetes.

Los módulos son los archivos .py, y se pueden importar para reutilizar el código que tengamos allí.

Los paquetes son carpetas, que dentro contienen otros directorios y archivos. La particularidad de los paquetes, es que contienen un archivo llamado `__init__.py`.


## Ejemplo: Módulos

``` python
import math
print(math.pi)
```

En este caso, estamos importando en nuestro código todo el contenido del módulo `math`, dentro del cual utilizamos la variable `pi`.

También podemos importar sólo una variable o método:

``` python
from math import pi
print(pi)
```

También se pueden renombrar los objetos que importemos, si es necesario:

``` python
import math as m
print(m.pi)
```
``` python
from math import pi as p
print(p)
```

## Librerías externas

Los imports nos sirven para agregar a nuestro código tanto módulos y paquetes propios, como elementos estándar de Python, y también librerías externas que instalemos en nuestro sistema.

### Entornos virtuales

En Python, para manejar las dependencias de nuestro código es muy común utilizar entornos virtuales, ya que nos ayudan a que no entren en conflicto las dependencias de todos los proyectos y nuestro propio sistema.

Los creamos con el siguiente comando, en una terminal:

```
> python -m venv entornovirtual
```

Luego una vez creado debe activarse, para que la terminal utilice esas dependencias:

```
> .\entornovirtual\Scripts\activate
```

### Instalación de otros sistemas

```
> pip install <nombre del paquete>
```

## Ejercicios:

1- Crear un entorno virtual en el directorio donde tengas los archivos Python del curso.

2- Instalar el paquete "Requests", el cual vamos a utilizar en la unidad siguiente: `pip install requests`.
