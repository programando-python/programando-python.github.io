.. title: 6-Funciones. Reutilización de código
.. slug: 6-funciones-reutilizacion-de-codigo
.. date: 2020-09-11 18:36:11 UTC-03:00
.. tags: 
.. category: 
.. link: 
.. description: 
.. type: text

Unidad 6
===========

Funciones
-----------------------
Hasta el momento estuvimos usando varias funciones de Python, que están incluidas en el lenguaje. Pero también podemos crear los propios, dandole un nombre e incluyendo la funcionalidad que necesitemos. Por ejemplo, así:

.. code:: python

    def saludar_usuario():
        nombre = input("¿Cuál es su nombre?")
        print("Bienvenido " + nombre + "!")

----

Muy bien, de esa manera extendimos las posibilidades del lenguaje, y ahora tenemos la función saludar_usuario() disponible!. Al igual que print() e input(), se pueden usar en nuestro programa. Para hacerlo, se deben invocar como cualquier otra función:

.. code:: python

    saludar_usuario()

----

Entonces, repasando: Para tener nuestras propias funciones en un programa, primero se deben definir (con la palabra reservada def), y luego se deben invocar.

----

Argumentos
--------------------

Una función puede recibir datos desde fuera, y de esa forma aumentar su funcionalidad. Para definirlos, se debe crear el nombre del argumento y separarlos con comas, dentro de los paréntesis:

.. code:: python

    def saludar(usuario):
        print("Bienvenido " + usuario + "!")
    
    def dividir(dividendo, divisor):
        print(dividendo / divisor)

----

Cuando se invocan las funcionen con parámetros, estamos obligados a completarlos todos. Se manejan de manera posicional; es decir que depende la posición en la que esté, significa a qué parámetro corresponde. También tenemos la posibilidad de nombrar explícitamente al parámetro, en tal caso ya no se manejarán posicionalmente.

.. code:: python

    saludar("Nahuel")

    dividir(35, 7)

    dividir(divisor=2, dividendo=50)

----

¿Cómo es el flujo de ejecución cuando invocamos una función?
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Tomemos este ejemplo para analizar:

.. code:: python

    def saludar(usuario):
        print("Bienvenido " + usuario + "!")
    
    saludar("Nahuel")
    print("Adiós")

----

- En primer lugar vemos la definición de la función "saludar". Esto debe aparecer primero en nuestro programa, porque de esa forma Python se entera que existe, y sabrá qué hacer cuando alguien quiera usarla.
- Luego, en la cuarta línea está la primera línea de código que será ejecutada: la invocación a la función "saludar". Toda la definición de la función es sólo eso, una definición. La invocación de "saludar" tiene el argumento entre paréntesis, que es "Nahuel". Ese es el dato que le llegará a la función cuando deba ejecutarse.
- El próximo paso, es ejecutar el código que tiene definido la función: la línea print. En este punto **sí** estamos ejecutando la función, y además el parámetro usuario tiene un valor, que es "Nahuel".
- Cuando el código de la función se ejecutó completamente, entonces el flujo sigue en la línea que continúa a la invocación de la función "saludar". Esto es el print del "Adiós".

----

Valores de retorno
------------------------

Es muy usual es que las funciones devuelvan algún valor, esto permite que en donde se haya invocado se reciba algún resultado de lo que se quería hacer. Mejoremos nuestra función de división:

.. code:: python

    def dividir(dividendo, divisor):
        resultado = dividendo / divisor
        return resultado

----

¿Notaron el cambio? No se está haciendo más un "print" del resultado, sino que aparece la palabra reservada *return* y luego la variable con el resultado. Esto producirá que donde se haya invocado, se reciba ese dato:

.. code:: python

    result = dividir(35, 7)
    print(result)

----

 Las funciones pueden o no retornar algún valor, por lo que el uso de *return* no es obligatorio.


Ejercicios:
----------------

1. Crear un programa que tenga una función que sume todos los números del 1 al 10, y devuelva el resultado.
2. Crear una función del factorial de un número: debe recibir por parámetro el número en cuestión, y retornar el valor calculado de su factorial.
3. Tomando como base el programa de la calculadora hecho en la unidad 4, ejercicio 4, crear funciones para cada una de las cuatro operaciones, y luego agregar sus respectivas invocaciones.

