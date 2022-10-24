<!--
.. title: 100 días de código: Día 2
.. slug: dia-2
.. date: 2022-10-15 09:09:41 UTC-03:00
.. tags: 100daysofcode
.. category: 
.. link: 
.. description: 100 días de código en Python: Input y variables
.. type: text
.. status: draft
.. author: Nahuel Tori
-->

# 100 días de código
## Input y Variables


## Día 2

### Leyendo la entrada del usuario

Vamos a ver cómo funciona el comando `input`. Se utiliza cuando el usuario debe ingresar información en la computadora. Es muy parecido al `print`, excepto que muestra un mensaje en la consola y luego _espera_ al usuario hasta que escriba algo en el teclado y aprete Enter.


Copia el siguiente código en el editor y apretá `run`:

``` python
input("¿Cuál es tu nombre?: ")
```



### Variables

Bien, `input` solicita algo al usuario, lo toma pero no tiene dónde ponerlo. Podemos cambiar eso con una `variable`, que es un valor que podemos usar para ponerle nombre y guardar datos.


``` python
nombreDeVariable = input("Nombre: ")
```

Aquí, `nombreDeVariable` es el nombre que le damos a nuestra variable, el cual crea un espacio en la memoria y donde podemos asignarle valores usando el símbolo `=`.


### Nombrando variables

* Las variable pueden tener cualquier nombre que desees, pero **no se pueden usar espacios**. Puedes usar:
  * guiones_bajos_entre_palabras
  * camelCaseParaFacilLectura

👉 Borrá todo el código de tu editor y copiá esto en el archivo `main.py`:
``` python
miNombre = input("¿Cuál es tu nombre?: ")
miEdad = input("¿Cuántos años tienes?: ")
print("Uh, ¡sos muy viejo!")
replit = input("¿Te gusta Replit? ")
print("¡Claro que te gusta!")
```

¡Bien! Ahora tenemos 3 variables:
- `miNombre` tiene el nombre del usuario guardado.
- `miEdad` guarda su edad.
- `replit` guarda qué siente el usuario sobre este sitio.

### Mostrando variables

Podemos ver el contenido de una variable imprimiendo su valor por la consola. Para eso, debemos usar la instrucción `print` y el nombre de la variable que usamos al otro lado del `=` en el comando `input`.  
En el código, ahora podemos conocer el nombre usando `print(miNombre)` o la edad usando `print(miEdad)`.

👉 Vamos a probarlo! Agrega este código al final y apreta`run`:
``` python
print()
print("Entonces, tu eres")
print(miNombre)
print("y con la asombrosa edad de")
print(miEdad)
print("y Replit para ti claramente es")
print(replit)
```

¿Pudiste ver lo que hizo `print()`?
* Si hay texto literal (con comillas dobles `" "` o simples `' '`) dentro de los `( )`, el texto es mostrado.
* Si hay un nombre de variable dentro de los `( )`, entonces se muetra el contenido de esa variable.
* Si no hay nada, entonces se muestra una línea en blanco.

Esta código se ve un poco raro, pero en breve ya lo vamos a mejorar.


### Posibles errores

_Primero, borra el código que haya en tu `main.py`. Luego, copia el bloque de código de ejemplo, aprieta `run` y mira qué errores aparecen. Arregla los errores y corre `run` de nuevo hasta que todo funcione._
_Al final podrás encontrar las soluciones._

#### Syntax Error

👉 Prueba el siguiente código en el editor. Luego, arreglalo hasta que funcione:

``` python
mi variable = input("¿Quién está ahí?")
print(mi variable)
```

¿Encontraste este error? ¿Qué podés arreglar?
```
  File "main.py", line 1
    mi variable = input("¿Quién está ahí?")
       ^
SyntaxError: invalid syntax
```


#### Name Error

👉 Prueba y arregla el siguiente trozo de código:

``` python
laAbuela = input("¿Cómo está la abuela? 😘")
print(laabuela)
```

```
¿Cómo está la abuela? 😘 bien
Traceback (most recent call last):
  File "main.py", line 2, in <module>
    print(laabuela)
NameError: name 'laabuela' is not defined
```


#### Respuestas

- Syntax Error: Hay un espacio en el nombre de la variable, lo viste? No usamos espacios en los nombres de variables.

- Name Error: La variable que intentamos mostrar **no** es la misma que creamos en primer lugar. La capitalización no es la misma. También sucederá lo mismo cuando queramos mostrar una variable que no creamos aun. **Siempre** hay que crear la variable antes de mostrarla.



#### Este sólo será raro...

👉 Prueba este código para ver qué pasa:

``` python
miAlmuerzo = input("¿Qué querés para almorzar? ")
print("Tu orden es la siguiente: ")
print("miAlmuerzo")
print("Lo antes posible!!")
```

```
¿Qué querés para almorzar? Sándwich
Tu orden es la siguiente: 
miAlmuerzo
Lo antes posible!!
```

* Respuesta:
- Quisimos mostrar una variable, pero quedó entre comillas!
- Recuerda: Las comillas imprimen literalmente lo que hay dentro.
- Si deseas mostrar el **contenido** de una variable, _no hay que usar_ comillas.


### Desafío del Día 2

1. Pregunta por el nombre del usuario, su comida favorita, música favorita y dónde vive. Puedes inventar algunas otras preguntas.
2. Guarda todas las respuestas en diferentes variables.
3. Imprime una oración completa que incluya todas las respuestas del usuario.
4. Agrega una línea al final con una afirmación positiva. Dile que es muy bueno en alguna de esas cosas!.



---

<br>

## Si pudiste resolverlo o necesitás ayuda:
¡Escribilo en los comentarios!  
Tu aporte, tanto sea de la solución como de cualquier pregunta, es bienvenido y le sirve a todos los que lean esto.  
También, podés leer [esta guía de ayuda](../../como-encontrar-ayuda.md) sobre cómo encontrar la información necesaria para resolverlo.

<br>

 ## ¿Qué aprendiste?
> Tomate un minuto para pensar qué aprendiste con este ejercicio.

- ¿Alguna nueva instrucción?
- ¿Por qué Python nos da funciones ya listas para usar?
- ¿Qué es el código fuente y qué es la ejecución de un programa?



<br>

¡Muy bien!  
Avancemos con el siguiente día: [Día 3](../dia-3).

<br>

