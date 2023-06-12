---
layout: post
title: "Un desbordamiento de enteros de 40 segundos"
date: "2023-06-12 15:00:00 +0000"
category: fallos
tags:
- fallos
- bugs
- desbordamiento
- enteros
- bugs
imagefeature: 'https://live.staticflickr.com/4413/37262365355_3b4457ce32.jpg'

---
<a href="https://www.flickr.com/photos/fernand0/37262365355/" title="Cohete Arianne "><img src="https://live.staticflickr.com/4413/37262365355_3b4457ce32.jpg" alt="Cohete Arianne " class="img-responsive img-centered"></a>

En [How a single line of code brought down a half-billion euro rocket launch](https://jam.dev/blog/famous-bugs-rocket-launch/) la historia del lanzamiento en 1996 del cohete Arianne 5 y su explosión 40 segundos después del lazamiento.

> Just 40 seconds after take-off, however, huge chunks of metal and burning fragments of Ariane Flight 501 are crashing down over the launch area. A shocking disaster for the ESA and a rough setback for the mission.

¿El problema? Un trozo de código, que provenía de la misión Arianne 4 y que ni siquiera se utilizaba.

> The cause? A simple, and very much avoidable coding bug, from a piece of dead code, left over from the previous Ariane 4 mission, which started nearly a decade before. Here’s what happened exactly.

El problema se debió a un fallo típico de desbordamiento pero de los que ni siquiera se suele hablar mucho: cuando se convierte un número real de 64 bits en uno de 16 bits con signo. 

>  To achieve this, the guidance system converts the velocity readings, from 64 bit floating point to 16 bit signed integer.

Si hacemos las cuentas, con 16 bits podemos almacenar cualquier número entre 0 y 65535 sin signo, y entre -32768 y 32767 si contemplamos números con signo.

> With 16-bit unsigned integers, you can store anything from 0 to 65,535. If you use the first bit to store a sign (positive/negative) and your 16-bit signed integer now covers everything from -32,768 to +32,767 (only 15 bits left for the actual number). Anything bigger than these values and you’ve run out of bits.

Por otra parte, los números reales se almacenan de manera diferente porque tṕicamente almacenan números más grandes y, además, deben gestionar la parte decimal (me gustó como lo cuentan en [Examples of floating point problems](https://jvns.ca/blog/2023/01/13/examples-of-floating-point-problems/), por ejemplo). 

En el caso del cohete, al almacenar un número real en las posiciones reservadas para un número entero se quedó sólo con la primera parte del mismo, generando un desbordamiento de enteros.

> Well, in this case, when the 16-bit signed integer was used, the conversion from float to integer wrapped around to the beginning again and finally ran into the very familiar integer overflow. Riight, so back to the rocket story.

El sistema de control detecta que los datos son inconsistentes, trata de arreglar el problema y (aquí viene el segundo problema) lanza el sistema secundario que ejecuta exactamente el mismo código.

> But wait a minute, there might be a saving chance! The system is designed to have a backup, standby system, which unfortunately, runs the exact same code. It tries the same conversion, gets the same error and just 72 milliseconds later, promptly crashes.

El sistema de control da por bueno el resultado, y el cohete recibe las instrucciones incorrectas.

Sin embargo, si este sistema ya se usaba anteriormente, ¿por qué no había fallado antes? Parece que el problema en este caso era que en las versiones del cohete la velocidad era menor y, por lo tanto, no tenían este problema.

> The same software was designed and used successfully on many flights previously, on the Ariane 4 rockets, which were much smaller. But the new Ariane 5 model was designed to fly faster than the systems engineers had planned when that code was originally created.

Finalmente, el código no era necesario después del despegue, así que no debería haber estado ejectutándose, pero para evitar reconfiguraciones en ese momento permitieron que ese código siguiera ejecutándose un poco más, ¡esos 40 segundos!

> The worst part? The code wasn’t necessary after takeoff, it was only part of the launch pad alignment process. But sometimes a trivial glitch might delay a launch by a few seconds and, in trying to save having to reset the whole system, the original software engineers decided that the sequence of code should run for an extra… 40 seconds after the scheduled liftoff.


