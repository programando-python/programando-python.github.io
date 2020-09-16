.. title: 5. Repetición simple: for
.. slug: 5-repeticion-simple-for
.. date: 2020-09-11 18:34:39 UTC-03:00
.. tags: 
.. category: 
.. link: 
.. description: 
.. type: text

Unidad 5
===========

Repetición Simple
-----------------------

Cuando necesitamos que un bloque de código se ejecute muchas veces, no lo copiamos y pegamos repitiéndolo muchas veces, sino que tenemos a disposición la estructura de repetición for, que usamos de la siguiente manera:

.. code:: python

    for numero in [0, 1, 2, 3, 4, 5]:
        print(numero)

----


Dentro del bloque de código del for, podemos tener cualquier tipo de código python que necesitemos.

----

La función **range()**
~~~~~~~~~~~~~~~~~~~~~~~~~~

Esta función nos devuelve una secuencia de una cantidad de números, comenzando por el 0 (por defecto) y creciendo de a 1 (por defecto). Dadas estas características, se utiliza mucho en conjunto con el for, para repetir un bloque de código una cantidad determinada de veces.

.. code:: python

    for num in range(8):
        print(num)
        
----

¿Qué pasó recién? Estamos ejecutando una repetición for, la cual repetirá tantas veces como elementos haya luego del "in". Estos elementos están dados por la secuencia que genera range(8), que son los números desde el 0 hasta el 7, en total 8 elementos.

Bien, en cada repetición el for va a estar utilizando cada uno de los valores de la secuencia, por lo que comienza con 0. El 0 lo guarda en la variable "num", y luego procede a ejecutar el bloque de código dentro del for: el print de la variable "num". En este primer ciclo, donde "num" tiene el valor 0, se mostrará en pantalla ese dato.  
Luego, comenzará el segundo ciclo de la repetición, donde "num" tomará el valor 1. Al ejecutarse el bloque de código del for, se mostrará en pantalla el 1. Luego, "num" tomará el valor 2, y así continuará ejecutandose cada ciclo hasta que no haya más elementos en la secuencia.


El for nos permite iterar, ir accediendo de a un elemento, sobre una colección de elementos. La anterior es una lista de números enteros. También podemos iterar otros tipos de colecciones, como las cadenas de caracteres:

.. code:: python

    for letra in "abcdefghijklmnñopqrstuvwxyz":
        print(letra)

----

La sentencia **continue**
~~~~~~~~~~~~~~~~~~~~~~~~~~

Esta palabra dentro del for nos permitirá cortar la ejecución del elemento actual. Esto significa, que todo el código que haya luego del **continue** no será ejecutado. Veamos en acción:

.. code:: python

    for letra in "abcdefghijkl":
        if letra == "c":
            continue
        print(letra)

----

La sentencia **break**
~~~~~~~~~~~~~~~~~~~~~~~~~~

Utilizando el **break** dentro del for, lo que producirá es que toda la repetición será detenida, por lo que no se ejecutará ningún otro ciclo más. Funciona así:

.. code:: python

    for letra in "abcdefghijkl":
        if letra == "h":
            break
        print(letra)

----

Ejercicios
-------------

1. Crear un programa que sume todos los números desde el 0 hasta el 10, y muestre el resultado en pantalla.
2. Crear un programa que pia un número al usuario, calcule su factorial y muestre el resultado en pantalla. El factorial de un número, es la multiplicación de todos los números desde 1 hasta ese mismo número. Por ejemplo, el factorial de 4 es 1 * 2 * 3 * 4 = 24.
3. Crear un programa que muestre en pantalla todas las letras de la frase: "Aprendiendo a programar con Python".
4. Crear un programa que pida al usuario el ingreso de una frase, cuente la cantidad de palabras que contiene y muestre el resultado en pantalla. A efectos prácticos de este ejercicio, vamos a considerar que una palabra es todo aquello que esté separado por un espacio " ".
