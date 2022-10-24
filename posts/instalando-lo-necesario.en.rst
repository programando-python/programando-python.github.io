.. title: Setting up your environment
.. slug: setting-up-your-environment
.. date: 2020-07-18 11:59:11 UTC-03:00
.. tags: 
.. category: 
.. link: 
.. description: 
.. type: text

Para poder trabajar cómodamente, lo mejor es tener acceso a una computadora personal en la cual escribir tus programas, guardarlos, probarlos y reutilizarlos.
Para eso, necesitamos que tenga instalado cierto software que repasaremos a continuación.

.. TEASER_END

Entorno Python
--------------

El más importante de todos es el mismo ambiente de programación de Python. Para descargarlo, entran a https://www.python.org/downloads/ y hacen click en el botón amarillo que dice "Download Python ...". Eso les va a descargar un archivo que se llama parecido a este: "python-3.8.4.exe", el cual deben guardar en su PC, y al finalizar deben ejecutarlo para que se instale el sistema.
Al terminar, si todo funcionó correctamente, en el menú del sistema (Windows?) se les tiene que haber agregado una carpeta llamada "Python 3.x.x".


Visual Studio Code
------------------

El siguiente será el entorno de desarrollo, en inglés llamado IDE: Visual Studio Code. Este es un programa hecho por Microsoft, que es libre, lo que significa entre otras cosas, que se puede descargar e instalar sin pagar nada ni violar ninguna licencia.
Para esto, deben entrar a https://code.visualstudio.com/ y hacer click en el botón azul que dice "Download for ...". Esto descargará un archivo que se llama parecido a "VSCodeUserSetup...", que también deben instalar como lo hicieron con Python.


Extensiones para el Visual Studio Code
--------------------------------------

Español
~~~~~~~~~

Cuando entren al Visual Studio Code, verán que está en inglés. Lo primero que vamos a hacer es pasarlo a español. Para esto, tenemos que hacer click en el botón de la barra izquierda llamado "Extensions", y que tiene un ícono en forma de cubos apilados. Allí en el buscador superior, tienen que ingresar la palabra "spanish", lo cual mostrará la extensión "Spanish Language Pack for Visual Studio Code". La seleccionan y hacen click en el botón verde "Install". Al finalizar, les pedirá reiniciar la aplicación, y ya estará configurada en español.

Python
~~~~~~

Luego instalaremos otra extensión más: "Python". Cuando busquen esta, van a aparecer un montón en los resultados: la que debemos instalar es la que se llama simplemente "Python", y está publicada por Microsoft. También deben instalarla haciendo click en el botón verde "Install".

¡Muy bien!

Para probar que todo funciona, vamos a hacer lo siguiente:

- Entramos al Visual Studio Code.
- Creamos un nuevo archivo, haciendo click en Archivo -> Nuevo archivo, o apretando Ctrl+N.
- Guardamos el archivo (Ctrl+S) con el nombre "prueba.py".
- Escribimos lo siguiente en el archivo:

.. code:: python

    print("¡Hola, bienvenido a programando con Python!")



- Hacemos click derecho sobre el texto del archivo, y elegimos la opción "Ejecutar archivo Python en la terminal".
- Si todo anduvo como preveíamos, entonces en la parte inferior debería abrirse una ventana y mostrar la línea que escribimos en nuestro programa.

¡Felicitaciones, escribiste tu primer programa!
