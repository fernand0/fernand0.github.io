---
layout: post
title: "Evaluación del generador de números seudo-aleatorios"
date: "Tue Jun 23 19:10:01 +0100 2015"
category: seguridad
tags:  seguridad PRNG RNG números aleatorios generador evaluación aleatoriedad random
---





<a href="https://www.flickr.com/photos/44124419077@N01/152110645/" title="Bolas en el bombo"><img src="https://farm1.staticflickr.com/49/152110645_43aafcb33c_m.jpg" width="240"  alt="Azar" style="float:left; margin:5px"></a>

Por algún motivo he estado leyendo unas cuantas cosas sobre generación de números aleatorios (la última vez en [Aleatoriedad y seguridad](http://fernand0.github.io/Aleatoriedad-Y-Seguridad/)) que no soy capaz de agrupar en menos entradas, así que vuelve a salir como tema recurrente. 

En [How do you know if an RNG is working?](http://blog.cryptographyengineering.com/2014/03/how-do-you-know-if-rng-is-working.html) justamente hablan de ese tema(afortunadamente con un enfoque diferente): ¿podemos confiar en nuestro generador de números aleatorios? Siempre se habla de que hay que medir la entropía pero no es algo que sea fácil de realizar ni que todo el mundo esté dispuesto a hacer.

> If you look at the literature on random number generators, you'll find a lot of references to statistical randomness testing suites like Diehard or NIST's SP 800-22. The gist of these systems is that they look a the output of an RNG and run tests to determine whether the output is, from a statistical perspective, "good enough" for government work (very literally, in the case of the NIST suite.)

Luego pasa a analizar las cosas que pueden ir mal (la propia inclusión de código para evaluar un generador podría introducir sus propios problemas, por ejemplo).
¿La conclusión?

> Solving this problem, at least in software, so we can ensure that code is correct and does not contain hidden 'easter eggs', represents one of the more significant research challenges facing those of us who depend on secure cryptographic primitives. I do hope some enterprising graduate students will give these issues the attention they deserve.

Que sería otro aviso de: no tratéis de hacerlo solos y en casa. O algo así.
