.. title: 6 - Ejercicios prácticos
.. slug: 6-ejercicios-practicos
.. date: 2020-09-30 20:06:21 UTC-03:00
.. tags: 
.. category: 
.. link: 
.. description: 
.. type: text

Unidad 6 - Ejercicios
=========================

Vamos a hacer algunos ejercicios adicionales, resumiendo todo lo que aprendimos hasta el momento.


1. Presten atención al siguiente código. Deben decir cuál será el próximo número que correspondería en la serie que se imprime. El que lo haga más rápido, gana.

.. code:: python

    cifra = 1
    diferencia2 = 7

    for diferencia1 in range(12):
        cifra = cifra + diferencia1
        cifra = cifra * diferencia2
        print(cifra)


2. Crear un programa que pida al usuario el ingreso de una frase, y luego por separado una letra. El programa debe recorrer toda la frase, y reemplazar todas las ocurrencias de esa letra, por un espacio.

3. Al programa anterior, agregarle que le pida al usuario una letra de reemplazo, para utilizar en lugar del espacio. Luego el programa debe buscar todas las ocurrencias de la primer letra, y reemplazarlas por la segunda.

4. Crear un programa que dibuje un edificio en pantalla con caracteres ASCII (ascii-art) como el que está debajo. El programa debe estar programado utilizando funciones, de acuerdo a las buenas prácticas de programación: cada función representa conceptualmente una parte de la casa, funciones más abstractas invocan a funciones más concretas, y deben reutilizarse cada vez que sea posible.

::

    ==================  
    |                |  
    |  ____    ____  |  
    |  |  |    |  |  |   
    |  ====    ====  |   
    |                |   
    |  ____    ____  |
    |  |  |    |  |  |
    |  ====    ====  |
    |                |
    |  ____    ____  |
    |  |  |    |  |  |
    |  ====    ====  |
    |     ______     |
    |     |    |     |
    |     |    |     |
    ==================


5. Crear un programa que dado un número que contenga cifras del 0 al 9, lo codifique de cualquier manera elegida por ustedes, y muestre el resultado. También dar la opción de poder ingresar un número codificado, y que devuelva el correcto.
