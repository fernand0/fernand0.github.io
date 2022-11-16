---
layout: post
title: "Pistas sobre la semilla para generar números aleatorios"
date: "Tue May 02 16:00:01 +0100 2017"
category: aleatorio
tags: [aleatorio, random, rng, generadores]
imagefeature: https://c2.staticflickr.com/2/1255/1301539362_daa1107f13_m.jpg
---




<a href="https://www.flickr.com/photos/fernand0/1301539362" title="Dados"><img src="https://c2.staticflickr.com/2/1255/1301539362_daa1107f13_m.jpg" width="240"  alt="Dados" style="float:left; margin:5px"></a>
Hacía tiempo que no traíamos el tema de la aleatoriedad. en [Random number generator seed mistakes](https://www.johndcook.com/blog/2016/01/29/random-number-generator-seed-mistakes/) hablan justamente de los errores más frecuentes en este tema, aunque no desde el punto de vista de la seguridad. Más bien les preocupan los aspectos de simulación.

Una primera solución (no muy buena desde el punto de vista de la seguridad, por su predecibilidad y/o posibilidad de control externo) es usar como semilla la hora. Desde luego, no es una buena idea pedir la semilla al usuario (sin, al menos, darle unas instrucciones razonables).

Pero la cosa se complica cuando trabajamos con hilos en paralelo:

> A more subtle problem I’ve seen with random number generator seeding is spawning multiple processes that each generate random numbers. In a well-intentioned attempt to give each process a unique seed, the developers ended up virtually assuring that many of the processes would have exactly the same seed.

No es una buena idea utilizar un generador aleatorio para generar las semillas, fundamentalmente porque no sería raro que se produzcan repeticiones:

> Suppose you seed each process with an unsigned 16-bit integer. That means there are 65,536 possible seeds. Now suppose you launch 1,000 processes. With 65 times as many possible seeds as processes, surely every process should get its own seed, right? Not at all.

Casi siempre, lo que parece simple no lo es tanto.
