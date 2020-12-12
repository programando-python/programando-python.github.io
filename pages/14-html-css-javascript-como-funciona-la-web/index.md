<!--
.. title: 14- HTML, CSS, Javascript. ¿Cómo funciona la web?
.. slug: 14-html-css-javascript-como-funciona-la-web
.. date: 2020-12-10 15:54:50 UTC-03:00
.. tags: 
.. category: 
.. link: 
.. description: 
.. type: text
-->

# Unidad 14

## HTML, CSS, Javascript. ¿Cómo funciona la web?

### HTML

Es un lenguaje de marcado de texto, que sirve para que los navegadores entiendan cómo deben mostrar la información en pantalla. Se basa en etiquetas, que le indican cómo se debe mostrar y tratar cada pieza de información.  
Este es un esqueleto básico de una página web:

``` html
<!DOCTYPE html>
<html>
<head>
</head>

<body>
    <h1>Título</h1>
    <p>Texto en un párrafo</p>
</body>
</html>
```

Una etiqueta se identifica con los signos <> y se cierra con </>; por ejemplo <p> y </p> en el ejemplo anterior, que sirven para delimitar un párrafo.  
* `<!DOCTYPE html>` sirve para indicar que el documento es de tipo HTML, y el navegador pueda mostrarlo apropiadamente.  
* `<html>` es la etiqueta principal que contiene todo el código de la página web.  
* `<head>` es una etiqueta que contiene información sobre la página web, metadata, que no se mostrará pero que sirve al navegador, buscadores y otras herramientas.
* `<body>` es la etiqueta donde va todo el contenido que será mostrado por el navegador.



Otras etiquetas importantes:

#### Encabezados o títulos

`<h1>` hasta `<h6>`, donde `<h1>` es el más importante, y `<h2>` es el que continúa luego en importancia.

#### Links o hipervínculos

La etiqueta `<a>` es la que se utiliza para crear un link a otra página. Se hace completando el atributo `href` con la dirección web de la página que queremos linkear.  
Por ejemplo:

``` html
<a href="https://www.w3schools.com/html">Link al sitio W3Schools sobre HTML</a>
```

#### Imágenes

Las imágenes se pueden incorporar en un sitio usando la etiqueta `<img>`. En el atributo `src` ponemos el nombre de la imagen, y ya funciona:

``` html
<img src="w3schools.jpg" alt="W3Schools.com" width="104" height="142">
```

Pueden ver otros atributos ahí. ¿Para qué se imaginan que deben servir?



### CSS

Las Cascading Style Sheets u hojas de estilo en cascada, se utilizan para describir cómo se deben mostrar los elementos HTML. Sirven para desacoplar de los datos HTML, la forma, color, fuente, estilo y demás ajustes en que los datos deben formatearse.  
Un gran beneficio es que puede escribirse en un archivo aparte, y éste ser referenciado por muchas páginas web, de esta forma dándole estilo a todas ellas al mismo tiempo. Estos archivos tienen extensión .css

#### Sintaxis: Ejemplo

``` css
p {
  color: red;
  text-align: center;
}
```

En CSS, primero se escribre el selector de la etiqueta, en este caso `p`. Luego, se indica cada propiedad que se quiere cambiar, y su valor.


### Javascript

Javascript es un lenguaje de programación que sirve para agregarle funcionalidad a las páginas web.  
Es ejecutado directamente por los navegadores web; no require instalación ni otro tipo de configuración.  
Es el lenguaje de programación más utilizado en Internet: la gran mayoría de las páginas web lo usan.

``` javascript
document.getElementById('demo').innerHTML = Date()
```


### Ejercicio:

1- Crear una página HTML utilizando la estructura básica antes descirpta. Agregarle un título con tu nombre, un párrafo explicando lo que hiciste ayer, y una imagen. También agregar un link a un sitio web.

