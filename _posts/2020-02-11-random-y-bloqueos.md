--- 
layout: post
title: "Aleatoriedad y bloqueos en el kernel de Linux"
date: "Tue Feb 11 15:05:01 +0100 2020"
category: aleatoriedad
tags: [aleatoriedad, random, linux, kernel]
imagefeature: https://live.staticflickr.com/49/152110645_43aafcb33c_m.jpg
---

<a href="https://flickr.com/photos/fernand0/152110645" title=" La suerte (?)"><img src="https://live.staticflickr.com/49/152110645_43aafcb33c_m.jpg" alt=" La suerte (?)" width="240" style="float:left; margin:5px"></a>
En esta ocasión traemos una entrada un poco técnica que habla de aleatoriedad. Se trata de [Really fixing getrandom()](https://lwn.net/Articles/802360/) y habla de las herramientas disponibles en el núcleo de Linux para generar aleatoriedad.

Es un tema que parece que se ha discutido con amplitud:

> The final days of the 5.3 kernel development cycle included an extensive discussion of the getrandom() API and the reversion of an ext4 improvement that was indirectly causing boot hangs due to a lack of entropy.

Y los problemas venían del bloqueo de getrandom() cuando en el sistema no había entropía suficiente:

>  The root of the problem in 5.3 was the blocking behavior of getrandom(), which will prevent a caller from proceeding until enough entropy has been collected to initialize the random-number generator.

No son cambios que se puedan hacer de cualquier forma, porque hay sistemas que confían en que estas funciones se comporten adecuadamente:

>  This behavior was subjected to a fair amount of criticism, and few felt the need to defend it. But changing getrandom() is not easy; any changes that might cause it to return predictable "random" numbers risks creating vulnerabilities in any number of security-sensitive applications.

Para evitar este bloqueo, se proponía asegurarse de que habría suficiente entropía para evitar los bloqueos.

> There is another way to ensure that getrandom() doesn't block during the bootstrap process: collect enough entropy to ensure that the random-number generator is fully initialized by the time that somebody needs it.

Una posibilidad era utilizar los mecanismos de la CPU cuando estuvieran disponibles:

> If the CPU has a hardware random-number generator, that can be used; some people distrust this solution, but mixing entropy from the hardware with other sources is considered to be safe by most, even if the hardware generator is somehow suspect.

Aunque esto no siempre es posible.

También se podría emplear una función que lee valores del contador de tiempos:

> On most architectures, random_get_entropy() just reads the timestamp counter (TSC) directly. The TSC increments for every clock cycle, so two subsequent calls should always return different values. Just how different they will be, though, is where the unpredictability comes in.

Y luego añadir un temporizador que expire los valores, de forma que todo sea un poco más complejo y, por lo tanto, menos predecible:

> The timer declared above is armed to expire in the near future (the next "jiffy", which be anytime between 0ms and 10ms); that expiration will happen by way of an interrupt and may occur on a different CPU.

Se calcula que esto añade un bit de entropía en cada expiración:

> In other words, every time the timer expires, the entropy pool is deemed to have gained one bit of entropy. 

Si el sistema espera al arrancar podría provocar pausas apreciables:

> ... potentially just over one second on a system with a 100HZ tick frequency — if the system in question has no other sources of entropy. That could result in a perceivable pause during the boot process, but it is far better than blocking outright. 

En definitiva, un artículo que se siguen bien para un problema interesante al que no siempre prestamos la debida atención.
o

Posteriormente se ha publicado [Removing the Linux /dev/random blocking pool](https://lwn.net/Articles/808575/)  continuando con el debate, aunque en términos ya menos técnicos.
