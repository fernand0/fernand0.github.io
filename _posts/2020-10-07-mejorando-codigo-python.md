--- 
layout: post
title: "Programación y coste en tiempo y en memoria"
date: "Wed Oct 07 15:02:01 +0100 2020"
category: python
tags: [desarrollo, coste, tiempo, memoria, programación, python]
imagefeature: http://live.staticflickr.com/3557/3407158925_632643109e.jpg
---

<a href="https://www.flickr.com/photos/fernand0/3407158925/" title="Memoria recursiva de Universa "><img src="https://live.staticflickr.com/3557/3407158925_632643109e.jpg" alt="Memoria recursiva de Universa " width="240" style="float:left; margin:5px"></a>
Esta entrada habla de Python, pero a veces por desconocimiento (o comodidad) no utilizamos todas las características de nuestros lenguajes favoritos y me pareció de interés.

En [Reduce Memory Usage and Make Your Python Code Faster Using Generators](https://www.securityartwork.es/2020/03/10/las-5-vulnerabilidades-mas-habituales-de-los-smart-contracts/) hablan de los generadores, como un mecanismo para gastar menos memoria y generar un código más eficiente en Python.

Técnicamente, un generador es una función que utiliza *yield* en lugar de *return* nos dice el autor.

> A generator looks a lot like a function, but uses the keyword yieldinstead of return. Let us take an example for better understanding.

Cuando hacemos una llamada tenemos un valor, pero con algunas característias interesantes. Por ejemplo, la función *next()*, que nos devolverá el siguiente valor generado por la función original (esto es, es una función que nos puede ir proporcionando valores sucesivos).

> The important thing to note is how state is encapsulated within the body of the generator function. You can also step through one by one, using the built-in next() function:

En Python podemos utilizar la función *range()* para generar una sucesión de valores, que genera(ba) un coste importante (según el tamaño, claro) en espacio y tiempo al ejecutarse.
Aunque allí no se dice, que hace mucho tiempo que teníamos *xrange()* y que en Python 3 *range()* también es un generador, con lo que el problema no sería tal.

En todo caso, parece que casi siempre merece la pena evaluar las consecuencias de las estructuras que utilizamos.
