.. title: 4- Alternativa condicional: if
.. slug: 4-alternativa-condicional-if
.. date: 2020-09-02 19:53:13 UTC-03:00
.. tags: 
.. category: 
.. link: 
.. description: 
.. type: text

Unidad 4
===========

Alternativa condicional
----------------------------

Una de las formas básicas para controlar el flujo de un programa, es la alternativa condicional. Nos permite evaluar una condición, y basado en el resultado, que el programa ejecute una porción de código u otra.

Tiene la siguiente forma:

.. code:: python

    if  "<condicion>" :
        "<código a ejecutar>"
    

En la condición puede haber cualquier expresión que se resuelva en verdadero (True) o falso (False).
Por ejemplo:

.. code:: python

    a = 0
    if a < 10:
        print("La variable a es menor a 10")

    
También podemos tener:

.. code:: python

    salir = False
    if salir:
        print("Gracias por usar este programa.")
        
En este ultimo caso, la linea con el print no se ejecutará, porque la condición es falsa.

Indentación
~~~~~~~~~~~~~~~~~~

Es lo que controla la porción de código que está dentro del if. Cada línea de código debe estar indentada de igual manera.

.. code:: python

    salir = False
    if salir:
        print("Gracias por usar este programa.")
    print("Esta línea se imprime siempre.")

        
En este último ejemplo, el anuncio de agradecimiento no se imprimirá, pero la línea siguiente si, ya que al no estar indentada no pertenece al bloque de código del if, sino al resto del programa.


Sino
~~~~~~

Cuando la condición no se cumple, no se ejecuta el código dentro, pero puede establecerse otra porción de código que se ejecutará cuando esto suceda.

Por ejemplo:

.. code:: python

    salir = False
    if salir:
        print("Gracias por usar este programa.")
    else:
        print("Seguimos trabajando.")

En este caso, el bloque de código dentro del else se ejecutará ya que la condición es falsa. Cuando la condición es verdadera, se ejecuta el código del if, pero **no** el del else, como acá:

.. code:: python

    a = 0
    if a < 10:
        print("La variable a es menor a 10")
    else:
        print("La variable a es mayor a 10")


Operadores
~~~~~~~~~~~~~~~~~~~

También podemos tener operadores dentro de nuestras expresiones, como vimos anteriormente:

.. code:: python

    a = 0
    b = 5
    if a < 10 and b > 5:
        print("La variable a es menor a 10")


Sino, si
~~~~~~~~~~~~~~

Hay una instrucción adicional que se llama "elif", y sirve para escribir varias condiciones encadenadas. Cuando la condición del if no se cumple, se puede preguntar por otra condición utilizando un elif, de esta manera:

.. code:: python

    a = 20
    b = 5
    if a < b:
        print("La variable a es menor a b")
    elif b < a:
        print("La variable a es mayor a b")
    else:
        print("Las variables son iguales")


Como pueden ver, al final de la última condición se cierra la estructura con un else, para chequear el resto de las posibilidades si es necesario.

Ejercicios
-------------

1. Escribir un programa en python que pida dos números al usuario, y que luego muestre en pantalla cuál es el mayor.
2. Escribir un programa que pregunte un nombre al usuario, lo chequee con un nombre de usuario almacenado en una variable del programa, y le responda si es el mismo que el guardado.
3. Escribir un programa que pida dos números al usuario, y también una operación que puede ser suma o resta. Luego, dependiendo del tipo de operación que se haya ingresado, debe sumar o restar los números, y mostrar el resultado en pantalla.
4. Al program anterior, agregar también las operaciones de multiplicación y división.


