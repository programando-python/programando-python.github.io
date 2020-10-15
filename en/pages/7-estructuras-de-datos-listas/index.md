<!--
.. title: 7-Estructuras de datos: Listas
.. slug: 7-estructuras-de-datos-listas
.. date: 2020-10-11 20:03:41 UTC-03:00
.. tags: 
.. category: 
.. link: 
.. description: 
.. type: text
-->

# Estructuras de datos: Listas

Vamos a conocer una de las formas básicas de organizar la información: las listas. Hasta el momento ya las habíamos usado, pero sin darnos cuenta.  
Una cadena de caracteres es una lista, y también la función range() nos devuelve una lista de números enteros.
Veamos ejemplos en el código:

``` python
numeros = [1, 2, 3, 4, 5]
semana = ["lunes", "martes", "miercoles", "jueves", "viernes"]
texto = "Este texto también es una lista, de caracteres"
```

## Iterar a través de una lista

Como ya aprendimos, utilizando el `for` podemos recorrer todos los elementos de una lista, uno por uno. Por ejemplo:

```python
for elemento in semana:
    print(elemento)
```

## Agregar elementos a una lista

Podemos agregarle elementos a una lista usando cualquiera de estas dos funciones: `append()` o `insert()`.

Agregar elementos al final:
``` python
semana.append("domingo")
```

Agregar elementos en una posición determinada:
``` python
semana.insert(5, "sabado")
```

## Acceder a elementos de la lista

Podemos utilizar el índice para acceder a un elemento de la lista, o modificarlo. El índice de las listas se utiliza mediante corchetes [].

``` python
print(semana[3])
semana[2] = "miércoles"
semana[5] = "sábado"
```

También podemos chequear si un determinado elemento existe en una lista utilizando el `in`, y preguntar cuál es su índice mediante la función `index()`.

``` python
if "lunes" in semana:
    print(semana.index("lunes"))
```

## Eliminar elementos de la lista

Utilizando `remove()` quitamos un elemento puntual. Con `pop()` vamos a remover el último de la lista, y `del` nos permite eliminar utilizando el índice.

``` python
semana.remove("miércoles")
semana.pop()
del semana[2]
del semana
```

Usando a la lista como condición, vamos a poder verificar si está vacía.
``` python
if not semana:
    print("La lista semana está vacía")
```

## Ejercicios

1. Dado el siguiente programa, completar las partes del código donde se debe agregar un item, modificar un item, eliminarlo, y mostrar la lista entera.
``` python
print("Lista recordatorio de compras del supermercado")
print("Elija la función a ejecutar:")
print("1: Listar elementos")
print("2: Agregar elemento")
print("3: Modificar elemento")
print("4: Eliminar elemento")
opcion = input("Elección: ")
super = []
if opcion == "1":

elif opcion == "2":

elif opcion == "3":

else:

```
2. Para cada una de las cuatro funciones agregadas anteriormente, crear una función que la realice, y reemplazar su código en el programa por la llamada a esa función.
