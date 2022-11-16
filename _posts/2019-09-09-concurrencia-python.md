--- 
layout: post
title: "Concurrencia en Python"
date: "Thu Sep 09 16:05:01 +0100 2019"
category: desarrollo
tags: [desarrollo, programación, concurrencia, python]
imagefeature: https://live.staticflickr.com/52/415859306_e77c449fd3_m.jpg
---

<a href="https://www.flickr.com/photos/fernand0/415859306" title="Hilos"><img src="https://live.staticflickr.com/52/415859306_e77c449fd3_m.jpg" width="240"  alt="Hilos" style="float:left; margin:5px"></a>
Por ahora Python no es el lenguaje de programación con mejores características de concurrencia (fundamentalmente, el intérprete no es lo que se llama `thread safe' así que hay que imponer restricciones para que las cosas funcionen  [Global Interpreter Lock](https://wiki.python.org/moin/GlobalInterpreterLock)).
Esto no significa que no haya primitivas para gestionar la concurrencia y que, en algunos casos, podamos obtener ventajas de la concurrencia.

Por eso (y porque la concurrencia es un tema que me gusta mucho) traigo aquí [An Intro to Threading in Python](https://realpython.com/intro-to-python-threading/) que me pareció una buena introducción al tema, didáctica y con ejemplos, sin olvidar el tema de las condiciones de carrera.

Allí también nos recuerdan que la concurrencia es limitada:

> But for most Python 3 implementations the different threads do not actually execute at the same time: they merely appear to.

Y que si queremos ir más allá tendremos que utilizar un intérprete no estándar:

> Getting multiple tasks running simultaneously requires a non-standard implementation of Python, writing some of your code in a different language, or using multiprocessing which comes with some extra overhead.

No obstante, es un tema interesante para explorar y siempre podremos obtener las ventajas típicas de la concurrencia, que consisten en poder hacer avanzar algunas tareas cuando otras se quedan atascadas (en operaciones de entrada/salida, o esperando algún evento, ...).
En otros casos no vamos a obtener una ventaja real, pero siempre está bien utilizar este lenguaje para aprender conceptos que luego pueden utilizarse en otros.
