---
layout: post
title: "Los fallos de seguridad en curl por culpa del lenguaje C"
date: "2021-09-28 15:00:00 +0000"
category: seguridad
tags:
- programación
- desarrollo
- vulnerabilidades
- lenguajes
- C
imagefeature: 'http://live.staticflickr.com/9/13391480_73b47df184.jpg'
---
<a href="https://www.flickr.com/photos/fernand0/13391480/" title="Another bug's life "><img src="http://live.staticflickr.com/9/13391480_73b47df184.jpg" alt="Another bug's life " width="240" style="float:left; margin:5px"></a>
Hace unos días hablábamos de la seguridad de Java (en [¿Java es un lenguaje seguro?  ](https://fernand0.github.io/java-seguro/). En cualquier caso, el récord como lenguaje problemático (aunque seguramente lo sea todavía más la programación en *shell*) lo tiene el lenguaje C.

En [half of curl’s vulnerabilities are C mistakes](https://daniel.haxx.se/blog/2021/03/09/half-of-curls-vulnerabilities-are-c-mistakes/) nos hablaban justamente de eso, para el caso de *curl*, la conocida herramienta que nos permite una amplia gama de posibilidades de transferencia de datos mediante URLs (que es una forma complicada de decir que puede hacer muchas de las cosas que hace un navegador; y algunas más, porque al poder integrarse en scripts tiene algunas ventajas interesantes). Viene de [Would Rust secure cURL?](https://blog.timhutt.co.uk/curl-vulnerabilities-rust/) donde se muestran los errores que provienen de las dificultades de C.

Daniel Stenberg, el responsable de curl se toma el trabajo de confirmar o desmentir estas ideas y llega a la conclusión de que la entrada proporciona datos ciertos (con pequeños matices de conteo).

> 51 out of 98 security vulnerabilities are due to C mistakes

> That’s still 52%.  

Pero claro, dice, el análisis se ha hecho sobre 98 fallos de los 6682 que ha tenido curl en su historia (un 1,46%).

>  The curl changelog counts a total of 6,682 bug-fixes at the time of this writing. It makes the share of all vulnerabilities to be **1.46% of all known curl bugs** fixed through curl's entire life-time, starting in March 1998

Luego nos cuenta cuáles son los tipos de fallos detectados: hay lectura fuera del espacio de memoria reservada (*buffer overread*),  y escritura, desbordamientos de memoria, (*buffer overflow*). También hay usos de la memoria después de liberarla (*user after free*) y liberaciones innecesarias (porque ya estaban hechas, *double free*). Finalmente, fallos relacionados con el NULL (*NULL mistakes*).

Sin embargo, nos dice, también es verdad que parece que las vulnerabilidades relacionadas con el lenguaje se encuentran antes que otros tipos de fallos.

> C mistake vulnerabilities are found on average at 80% of the time other mistakes need to get found. Or put the other way around: mistakes that were not C mistakes took 25% longer to get reported – on average. I’m not convinced the difference is very significant. 

Un poco de numerología y también un recordatorio que los fallos de seguridad no siempre tienen que ver con los fallos del lenguaje, hay más posibilidades de equivocarse y son más difíciles de encontrar.
