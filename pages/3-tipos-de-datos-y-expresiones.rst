.. title: 3-Tipos de datos y expresiones
.. slug: 3-tipos-de-datos-y-expresiones
.. date: 2020-08-16 17:47:55 UTC-03:00
.. tags: 
.. category: 
.. link: 
.. description: 
.. type: text

Unidad 3
-----------

`Tipos de datos en Real Python <https://realpython.com/python-data-types>`__

En Python, aprendimos que para definir una variable debemos nombrarla y asignarle un valor. El valor que le asignamos a la variable define su tipo de dato. El tipo de dato se refiere a qué forma tiene su contenido: ¿es un número? ¿es texto? ¿hay otros tipos de datos?

Hasta el momento, solamente vimos y usamos un tipo de dato: cadena de caracteres o comunmente llamado "string". Hay varios tipos más de datos en Python, y vamos a ver los más usados.

Enteros
~~~~~~~~
Un número entero puede ser del largo que sea necesario, no tiene límite. 

.. code:: python

    numero = 123456
    largo = 98765432101234567890987654321012345678909876543210
    
    type(numero)
    type(largo)
     

Si ejecutamos el código anterior, podemos ver que la función "type" devuelve 'int', que significa 'integer'.

Decimales
~~~~~~~~~~~
Los números de punto flotante, comunmente llamados decimales, se especifican utilizando un punto dentro del número.

.. code:: python

    decimal = 1.8
    medio = .5

    type(decimal)
     

También se puede utlilizar notación científica, agregando una 'e' o 'E' seguido de un número positivo o negativo:

.. code:: python

    pequeño = 523e-6
    enorme = 8e15
    print(pequeño)
    print(enorme)


Cadenas de caracteres
~~~~~~~~~~~~~~~~~~~~~~~~~

Las cadenas o "strings" son secuencias de caracteres. Para especificar un string, lo hacemos encerrando el texto con comillas simples o dobles, ' o ".

.. code:: python

    texto1 = "Esto es un string"
    texto2 = 'Esto también'

    texto3 = "Un string no puede contener el delimitador de comillas " dentro así nomás"


Podemos escribir un texto que contenga comillas, usando las otras como delimitador:

.. code:: python

    texto1 = "Este string tiene una ' comilla"
    texto2 = 'Este string tiene " comillas dobles'


Caracter de escape: \ . Utilizando una barra invertida, podemos saltear el error de un caracter especial, como las comillas:

.. code:: python

    texto1 = "Este string tiene unas \" comillas dobles"


De esta forma, hay determinados caracteres especiales que podemos utilizar:

- \n  --> Nueva línea
- \t  --> Tabulación horizontal
- \b  --> Backspace o vuelta atrás

.. code:: python

    texto1 = "Este texto \n tiene dos líneas"
    texto2 = "Este texto está \t tabulado"


Booleanos
~~~~~~~~~~~

Los tipos de datos booleanos tienen dos posibles valores: True o False, verdadero o falso. Los utilizamos para determinar condiciones e interpretar expresiones, como veremos en breve.

.. code:: python

    verdadero = True
    falso = False

    type(verdadero)
    type(falso)



Casteos de datos
~~~~~~~~~~~~~~~~~~~~~~~

Castear una variable se refiere a transformar su tipo de dato en otro. Por ejemplo, un número en un texto, o un decimal a entero.

.. code:: python

    entero_desde_texto = int("10")
    texto_desde_float = str(1.25)
    float_desde_texto = float("2.5")
    entero_desde_float = int(10.8)


Estas funciones incluidas en Python nos ayudan a transformar el tipo de dato de una variable cuando lo necesitemos.


Expresiones
~~~~~~~~~~~~~~

Las expresiones están formadas mediante datos o variables y diferentes operadores. Cada operador funciona de una determinada manera según el tipo de dato.

`Operadores en w3schools <https://www.w3schools.com/python/python_operators.asp>`__

* Operadores aritméticos:

.. code:: python

    suma = 1 + 2
    resta = 10 - 8
    multiplicacion = 2 * 4
    division = 8 / 2

    concatenacion = "Hola" + ", cómo te va?"
    copiado = "Hola " * 4


* Operadores de comparación:

.. code:: python

    5 == 2 + 3
    "Hola" != "Chau"
    10 < 10 + 5
    1 > 1 + 1


* Operadores lógicos:

.. code:: python

    operador_y = 2 < 5 and 2 < 10
    operador_o = 1 < 4 or 10 > 20
    operador_no = not(5 == 2 + 3)

    print(operador_y)
    print(operador_o)
    print(operador_no)


El resultado de la expresión es lo que Python devuelve luego de evaluarla. Entonces, el resultado de la expresión 1 + 3 es 4, y el de 1 + 3 == 5 es False.
Las expresiones de comparación, en las cuales el resultado es un booleano verdadero o falso, nos van a servir cuando veamos alternativa condicional (o if), el tema que viene.



Ejercicios
~~~~~~~~~~~~
1- Escribir un programa que pregunte dos números diferentes al usuario, luego los sume y finalmente muestre el resultado en pantalla.
2- Ídem al programa anterior, pero que reste el segundo número al primero.
3- Escribir un programa que pida al usuario el ingreso de un texto cualquiera, y luego un cantidad de veces a repetirlo. Mostrar en pantalla el texto ingresado, repetido tantas veces como haya solicitado el usuario.
4- Ídem al programa anterior, pero entre cada repetición de texto, agregar un separador de nueva línea.
5- Pedir al usuario que ingrese por pantalla dos números. Luego evaluar si la suma de ellos es mayor que su multiplicación, y mostrar un mensaje en pantalla indicando eso. El mensaje a mostrar puede ser algo como: "La suma de los números <X> y <Y> es mayor que la multiplicación de <X> y <Y>: <True/False>"
