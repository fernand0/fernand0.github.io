---
layout: post
title: "Las vulnerabilidades y su estudio para mejorar la seguridad"
date: "2023-10-16 15:00:00 +0000"
category: seguridad
tags:
- seguridad
- vulnerabilidades
- estudio
- análisis
imagefeature: 'https://live.staticflickr.com/65535/53157960327_4382174f80.jpg'
---
<a href="https://www.flickr.com/photos/fernand0/53157960327/" title="Catedral de Santa Cecilia. Detalle superior. "><img src="https://live.staticflickr.com/65535/53157960327_4382174f80.jpg" alt="Catedral de Santa Cecilia. Detalle superior. " class="img-responsive img-centered"></a>

En [2022 0-day In-the-Wild Exploitation…so far](https://googleprojectzero.blogspot.com/2022/06/2022-0-day-in-wild-exploitationso-far.html) Maddie Stone del proycto Google Project Zero habla de los fallos de día cero (fallos para los que todavía no hay una actualización que resuelva el problema) y cómo son.

Empieza diciendo que en junio de 2022 había 18 de estos fallos detectados y que estaban siendo utilizados por los malos, pero que la mitad de ellos eran simplemente variantes de fallos anteriores que no habían sido adecuadamente resueltos.
Esto significa que podrían haberse evitado si el arreglo hubiera podido realizarse con más cuidado.

> As of June 15, 2022, there have been 18 0-days detected and disclosed as exploited in-the-wild in 2022. When we analyzed those 0-days, we found that at least nine of the 0-days are variants of previously patched vulnerabilities. At least half of the 0-days we’ve seen in the first six months of 2022 could have been prevented with more comprehensive patching and regression tests. 

Esto es totalmente contradictorio con la idea que tenemos a veces de que estos fallos son muy sofisticados y tecnológicamente avanzados.

> When people think of 0-day exploits, they often think that these exploits are so technologically advanced that there’s no hope to catch and prevent them.

El problema es que cuando se encuentran este tipo de fallos no suele disponerse de la tranquilidad y el tiempo necesario para solucionarlos bien y lo que se hace es evitarlos de la mejor manera posible que sea rápida y luego ya no hay más tiempo ni interés en mejorar esa solución.

Haría falta encontrar la verdadera causa del problema y cómo se ha podido llegar a introducir el fallo.

> Understanding the underlying vulnerability that is being exploited. Also tries to understand how that vulnerability may have been introduced.

Haría falta analizar las posibles variantes del problema que podrían afectarnos: buscar el mismo patrón en otros lugares, y hacer mejores comprobaciones.

> Looking for other vulnerabilities similar to the reported vulnerability. This can involve looking for the same bug pattern elsewhere, more thoroughly auditing the component that contained the vulnerability, modifying fuzzers to understand why they didn’t find the vulnerability previously, etc. 

Habría que analizar el parche (la solución) para estar seguros de que resuelve el problema de manera completa.

> Analyzing the proposed (or released) patch for completeness compared to the root cause vulnerability. 

Finalmente, comprender cómo se realiza el ataque y cómo se usa el fallo, para taratar de resolver no sólo el fallo, sino también mitigar la posibilidad de que se utilicen técnicas similares en otros contextos.

> Understanding the primitive gained from the vulnerability and how it’s being used. While it’s generally industry-standard to patch vulnerabilities, mitigating exploit techniques doesn’t happen as frequently. 

Todo ello, claro, compartido de manera transparente por los afectados, de forma que todo el mundo pueda aprender de esos problemas.
