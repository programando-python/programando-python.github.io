<!--
.. title: 8. Repetición condicional: while
.. slug: 8-repeticion-condicional-while
.. date: 2020-10-15 15:36:01 UTC-03:00
.. tags: 
.. category: 
.. link: 
.. description: 
.. type: text
-->

# Unidad 8
## Repetición condicional: While

Así como ya aprendimos sobre la repetición simple con el for, también podemos generar bucles o repeticiones que estén controlados por una condición.

De esta manera, podremos crear código que se ejecute un número indefinido de veces, y que esto sea controlado mediante una expresión.

``` python
dia = "viernes"
while dia != "viernes":
    print("Aun no llega el fin de semana :("))
    dia = input("Qué día es?")
```

La palabra reservada que nos permite esto es `while`. Luego aparece la expresión, que mientras sea verdadera permitirá que el bucle se siga ejecutando.


### La sentencia else

Usando `else`, podemos ejecutar una porción de código cuando la condición ya no se cumpla más. No es de uso obligatorio.

``` python
dia = "viernes"
while dia != "viernes":
    print("Aun no llega el fin de semana :("))
    dia = input("Qué día es?")
else:
    print("¡Al fin llegó el fin de semana!")
```

### Las sentencias continue y break

Estas dos sentencias funcionan igual que en el `for`. Recordemos como eran, pero en el contexto de `while`.

``` python
contador = 0
while contador < 10:
    print contador
    contador += 1
```

En este bucle, imprimimos los números del 0 al 9.

#### continue

``` python
contador = 0
while contador < 10:
    if contador == 5:
        continue
    print contador
    contador += 1
```

La instrucción `continue` genera que ese ciclo sea abortado, no se ejecuten más líneas desde que aparece el continue. El bucle continúa directamente con el próximo.

#### break

``` python
contador = 0
while contador < 10:
    if contador == 5:
        break
    print contador
    contador += 1
```

La instrucción `break` genera que se interrumpa por completo el bucle. Nada más se ejecuta, y el programa continúa con la intrucción siguiente al `while`.

### Ejercicios

1. Escribir un programa con un bucle que se ejecute mientras un contador llamado "a" sea mayor a 0. En cada iteración, se debe restar 1 al valor del contador.
2. Crear una variable con un número al azar entre el 0 y 10. Luego pedir al usuario mediante teclado que "adivine" el número, indicandole que está entre el 0 y 10. Si el usuario no acierta, seguir preguntando hasta que lo haga. Cuando acierte, notificarlo y terminar el programa.
3. Siguiendo el programa creado en la unidad 7, vamos a agregar el uso del menú: a. Agregar una nueva opción para el usuario que sea "x: Salir". b. Agregar un bucle a la ejecución del programa, en donde la condición del bucle sea que la opción que ingresó el usuario sea diferente a "x".
