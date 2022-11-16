---
layout: post
title: Teoría de la aleatoriedad y seguridad
date: 2021-03-15 15:00:00 +0000
category: seguridad
tags:
- seguridad
- aleatoriedad
- random
- teoría
- complejidad
imagefeature: 'http://live.staticflickr.com/65535/50338054856_60589bb8da.jpg'

---
<a href="https://www.flickr.com/photos/fernand0/50338054856/" title="Reloj "><img src="http://live.staticflickr.com/65535/50338054856_60589bb8da.jpg" alt="Reloj " width="240" style="float:left; margin:5px"></a>
En seguridad informática suele hablarse de aletoriedad, aunque en los sitios habituales de divulgación no tanto. Por eso vamos recopilando aquí todas las noticias que encontramos sobre el tema que llaman nuestra atención. Con las teorías pasa lo mismo, solo hablamos de las que nos gustan, y el resto del tiempo las teorías son cosas molestas que nos llevan lejos del 'mundo real'.

Hoy traemos [Randomness theory could hold key to internet security](https://news.cornell.edu/stories/2020/07/randomness-theory-could-hold-key-internet-security)

Se habla de criptografía, un esquema común de cifrado que se basa en la descomposición de números en factores primos y la creencia de que no existen métodoso eficientes para realizar esta descomposición.

> It is believed that no efficient factoring algorithm exists for large numbers, Pass said, though researchers may not have found the right algorithms yet.


También se habla de la complejidad de Kolmogorov que permite medir la cantidad de aleatoriedad que incluye una cadena de números.
La definición mide esa complejidad por el tamaño del programa más corto que puede generar la cadena.

> Meanwhile, mathematicians in the 1960s identified what’s known as Kolmogorov Complexity, which refers to quantifying the amount of randomness or pattern of a string of numbers. The Kolmogorov Complexity of a string of numbers is defined as the length of the shortest computer program that can generate the string; 

Para aligerar el problema (ese programa podría ser muy costoso) se introdujo el concepto de complejidad de Kolmogorov acotada en tiempo. Esto es, la longitud de un programa que puede generar la secuencia en una cierta cantidad de tiempo.

> ... researchers in the Soviet Union in the 1960s, as well as Hartmanis and others in the 1980s, developed the time-bounded Kolmogorov Complexity – the length of the shortest program that can output a string of numbers in a certain amount of time.

Las consecuencias de estos trabajos son que si pudiéramos encontrar un programa para resolver el problema de la complejidad de Kolmogorov acotada en tiempo para un número significativo de situaciones, podríamos romper todos los sistemas criptográficos. Si no, podemos estar seguros de que podemos encontrar buenas funciones de cifrado que sean seguras.

> "If you can come up with an efficient algorithm to solve the time-bounded Kolmogorov complexity problem for a large fraction of things, then you can break all crypto, all encryption schemes, all digital signatures," Pass said. “However, if no efficient algorithm exists to solve this problem, you can get a one-way function, and therefore you can get secure encryption and digital signatures and so forth.”

Y eso son cosas que hay que saber.
