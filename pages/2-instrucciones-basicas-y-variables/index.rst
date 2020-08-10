.. title: 2-Instrucciones básicas y variables
.. slug: 2-instrucciones-basicas-y-variables
.. date: 2020-08-09 20:22:42 UTC-03:00
.. tags: 
.. category: 
.. link: 
.. description: 
.. type: text

Unidad 2
-----------

Vamos con el primer programa que todo programador hace al aprender un nuevo lenguaje:

.. code:: python

    print("Hola mundo!")


Esta instrucción "print" muestra en pantalla lo que sea que le pongamos dentro de los paréntesis.

Todo lo que está entre comillas "Texto" es un texto literal.


Vamos a crear una variable, definiendo su nombre y asignándole un valor.

.. code:: python

    nombre = "Nahuel Tori"

    print(nombre)

En este último caso imprimimos en pantalla el contenido de nuestra variable, no el nombre, ya que no está entre comillas.


.. code:: python

    nombre = "Nahuel Tori"

    print("Hola, " + nombre)

Acá combinamos la impresión de un texto literal, con el contenido de una variable, mediante el uso del operador "+".


.. code:: python

    nombre = input("Decime, ¿cuál es tu nombre?")

Esta es una nueva instrucción: sirve para que el programa pida información al usuario a través del teclado.

Estas instrucciones son funciones que ya vienen creadas en Python. La función "input" primero imprime en pantalla el mensaje que se le envía en los paréntesis, al igual que "print". Pero luego de eso, quedará el cursor esperando que el usuario escriba en el teclado lo que quiera, hasta apretar "Enter".

La información que el usuario haya ingresado, será lo que la función devuelva, y en este caso será el valor que se le asigne a la variable "nombre".

Podemos comprobarlo, si mostramos en pantalla el contenido de "nombre".

.. code:: python

    nombre = input("Decime, ¿cuál es tu nombre?")

    print("Hola, " + nombre)



Veamos algunos ejemplos más:

.. code:: python

    print("¡Buenos días!")
    print("¿Cómo estás hoy?")

    edad = input("¿Cuántos años tenés?")
    vacaciones = input("¿A dónde te pensás ir de vacaciones?")



Importante:

- **Sintaxis**: Cada línea de código debe estar escrita correctamene, sin erroes, siguiendo la sintaxis del lenguaje. Sino, al intentar ejecutarlo se mostrará un error.
- **Intérprete**: Como aprendimos anteriormente, al ejecutar nuestro programa, el intérprete de Python lee nuestro código y lo transforma en instrucciones que la computadora pueda entender. Siempre realizará exactamente lo que escribimos, no más, no menos.


Ejercicios
~~~~~~~~~~~~

1. Escribir un programa en Python que muestre, en diferentes líneas, la siguiente información: nombre y apellido, ciudad y país donde vivo, cantidad de integrantes de mi familia.
2. Escribir un programa que pregunte al usuario cuál es el clima en ese momento, y luego muestre en pantalla el estado del clima actual.
3. Agregar al programa anterior, que también pregunte cuál es la ciudad en la que se encuentra el usuario, y que a la información que se muestra en pantalla también se indique cuál es la ciudad.
4. Imaginemos que nos encontramos con el siguiente problema: Debemos enviar 50 emails a destinatarios diferentes, avisándole el estado en que se encuentra su pedido. Escribir un programa que pregunte la siguiente información y la guarde en diferentes variables: Nombre del destinatario, código de envío, estado del envío. Luego, el programa debe mostrar en pantalla un texto como el siguiente, pero incluyendo la información consultada previamente en las partes indicadas entre llaves {}: "Hola {nombre del destinatario}, muchas gracias por tu compra. Te queremos avisar que el pedido que nos realizaste tiene el código {códgio de envío}, y se encuentra actualmente {estado del envío}. Muchas gracias."

