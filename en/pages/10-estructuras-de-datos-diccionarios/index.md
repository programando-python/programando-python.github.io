<!--
.. title: 10. Estructuras de datos: diccionarios.
.. slug: 10-estructuras-de-datos-diccionarios
.. date: 2020-11-12 15:22:10 UTC-03:00
.. tags: 
.. category: 
.. link: 
.. description: 
.. type: text
-->

# Unidad 10

## Estructuras de datos: Diccionario

Una estructura de datos muy utilizada en Python es el diccionario, o 'dict'. Se trata de pares de key-values o claves y sus valores, asociados, que guardan la información en la estructura.

``` python
datos = {"a": 1, "b": 2, "c": 3}
```

### Acceder a los elementos

Obtenemos los valores en un diccionario, accediendo por su clave:

``` python
x = datos["a"]
```

También podemos usar el método get():

``` python
x = datos.get("a")
```

### Actualizar datos

Podemos actualizar los datos de un determinado elemento, refiriéndolo por su clave:

``` python
datos["b"] = 5
```

### Recorrer todos los datos de un diccionario

Para iterar los elementos de un diccionario, los recorremos utilizando la estructura `for`. Cuando pasamos por sus elementos de esta manera, el elemento que obtenemos es la **clave**.

``` python
for x in datos:
    print(x)
```

Para iterar los **valores**, debemos hacer:

``` python
for x in datos:
    print(datos[x])
```

O también:

``` python
for x in datos.values():
    print(x)
```

También tenemos la posibilidad, muy útil a veces, de obtener ambos valores **clave** y **valor** en cada iteración:

``` python
for x, y in datos.items():
    print(x, y)
```

### Chequear la existencia de una clave

Esta utilidad es muy importante, ya que si queremos acceder a una clave que no existe obtendremos un error.

``` python
print(datos["e"])

if "c" in datos:
    print("La clave 'c' existe en el diccionario datos.")
```

### Agregando elementos

Para agregar datos al diccionario, simplemente referenciamos la nueva clave asignándole un valor:

``` python
datos["d"] = 10
```

### Eliminar un elemento

Al igual que con las listas, para eliminar elementos hay varias formas:

``` python
datos.pop("b")       # Elimina el elemento indicado
datos.popitem()      # Elimina el último elemento
del datos["c"]       # Elimina el elemento indicado
datos.clear()        # Vacía por completo el diccionario
del datos            # Elimina todo el objeto diccionario
```

### Copiar diccionarios

Con los tipos de datos que conocíamos hasta el momento, podíamos copiar un elemento simplemente asignándolo a uno nuevo. Pero con los diccionarios, esto no funciona, ya que solamente estaríamos copiando su *referencia*. Para copiarlo completamente, debemos utilizar el método `copy()`.

``` python
nuevoDicc = datos.copy()
print(nuevoDicc)
```

### Ejercicios

1- Dada la siguiente estructura inicial de un programa Python, completar el código necesario para mostrar los elementos, agregar uno nuevo, modificar uno existente, eliminar uno y para salir. Como clave del diccionario utilizaremos el nombre del libro, y como valor, el nombre de la persona a quien se lo prestamos.

``` python
print("Archivo de libros prestados")
salir = False

while not salir:
    print("Elija la función a ejecutar:")
    print("1: Mostrar datos")
    print("2: Agregar elemento")
    print("3: Modificar elemento")
    print("4: Eliminar elemento")
    print("5: Salir")
    opcion = input("Elección: ")
    libros = {}
    if opcion == "1":

    elif opcion == "2":

    elif opcion == "3":

    elif opcion == "4":
    
    elif opcion == "5":


```

2- Idealmente, al realizar el ejercicio anterior, cada parte del código podemos agregarlo como una nueva función de forma que el código quede más ordenado y legible.

