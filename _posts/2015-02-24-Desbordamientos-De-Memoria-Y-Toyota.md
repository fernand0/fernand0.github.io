---
layout: post
title: "Desbordamientos de memoria y Toyota"
date: "Tue Feb 24 23:55:01 +0100 2015"
category: seguridad
tags: [seguridad, toyota, accidentes, fallos, desbordamiento, memoria, pila, stack, overflow, coches]
---



<a href="https://www.flickr.com/photos/fernand0/2968897323/" title="En la carretera"><img src="https://farm4.staticflickr.com/3189/2968897323_a296cc521b_m.jpg" width="240"  alt="Coches y carretera" style="float:left; margin:5px"></a> 
Interesante documento en [Are We Shooting Ourselves in the Foot with Stack Overflow?](http://embeddedgurus.com/state-space/2014/02/are-we-shooting-ourselves-in-the-foot-with-stack-overflow/) donde se hace un resumen de los problemas con los aceleradores de algunos modelos de Toyota. El fallo se atribuye a un desbordamiento de memoria (concretamente en la pila) y cómo esto podía producir que determinadas variables (del sistema) se vieran alteradas, con consecuencias.

De hecho, parece ser uno de los peores casos de corrupción de variables por desbordamiento de memoria, porque en lugar de manifestarse inmediatamente (en este caso, probablemente a baja velocidad todavía) aparecía algo más tarde con las consecuencias ya conocidas.

Luego propone algunas medidas que podrían mejorar la situacion, tanto desde el punto de vista de la gestión de memoria como del sistema operativo y las pruebas (tests).

En [The Toyota Owners Left Holding the Bag](http://www.safetyresearch.net/blog/articles/toyota-owners-left-holding-bag) podemos leer una descripción que simplemente habla de 'código espagueti', algunas consecuencias legales, los seguros...

**Actualización (2015-03-01)** Nos enlazó Juanjo Navarro [ fernand0 @ GitHub.io y recursividad ](http://www.juanjonavarro.com/2015/02/25/fernand0-githubio-y-recursividad) y lo agradecemos aquí. Casi seguro que volveremos sobre este enlace acerca de nuestros sesgos y enfoques. Y también que hablaremos alguna vez de lo que Juanjo hable en su sitio. ¡Gracias!
