<!--
.. title: 9. Proyecto: Juego Ahorcado
.. slug: 9-proyecto-juego-ahorcado
.. date: 2020-10-29 17:33:09 UTC-03:00
.. tags: 
.. category: 
.. link: 
.. description: 
.. type: text
-->

¡Muy bien!
Ya llegaste a la mitad del curso. Para esta ocasión, vamos a tomarnos la clase en armar un juego: el Ahorcado.

El juego tiene las siguientes reglas:

* Participan 2 jugadores, uno que propone una palabra secreta a adivinar, y otro que intenta adivinarla nombrando letras del abecedario.
* Debe mostrarse un guión por cada letra de la palabra secreta.
* Por cada letra nombrada que esté contenida en la palabra secreta, debe descubrirse su posición.
* Por cada letra nombrada errónea, se debe dibujar una nueva parte de nuestro muñeco ahorcado.
* El ahorcado posee seis partes: cabeza, cuerpo, brazos y piernas. Esto significa que se tienen 5 posibilidades de equivocarse: en la sexta, el juego se termina y el jugador pierde.
* El juego también se termina cuando todas las letras de la palabra secreta son descubiertas.


Algunos detalles para pensar cuando implementemos el juego:

1. ¿Cuántas posibilidades de equivocarse hay? Hay que llevar la cuenta.
2. ¿Cuales son las condiciones bajo las que el juego (su programa) se termina?
3. De alguna forma necesitaremos verificar si la letra que el usuario ingresa pertenece a la palabra oculta.
4. ¿Qué tareas debemos realizar cada vez que el usuario intenta adivinar una letra?

