---
layout: post
title: "Condiciones de carrera en algunos sitios famosos"
date: "Mon Dec 21 13:10:01 +0100 2015"
category: seguridad
tags: [seguridad, concurrencia, web, condiciones, carrera, fallos, errores, vulnerabilidades, Facebook, DigitalOcean, LastPass]
---




<a href="https://www.flickr.com/photos/fernand0/3221352728" title="Carrera"><img src="https://c2.staticflickr.com/4/3099/3221352728_6729819d04_m.jpg" width="240"  alt="Carrera" style="float:left; margin:5px"></a>
Cuando explicamos las condiciones de carrera siempre nos quedamos con la duda de si es un tema que ya todo el mundo conoce y también si no sería mejor dedicar ese tiempo a explicar otras cosas. 
De pronto, una entrada como [Race conditions on Facebook, DigitalOcean and others (fixed) ](http://josipfranjkovic.blogspot.com.es/2015/04/race-conditions-on-facebook.html) nos demuestra que más vale no olvidarlos.

Las condiciones de carrera ocurren en sistemas concurrentes, cuando dos actores acceden a o modifican una determinada información y el tiempo y la forma de acceso son importantes, porque lo que haga uno de ellos afecta a lo que el otro debería poder hacer. Se puede ver una explicación en [Practical Race Condition Vulnerabilities in Web Applications](https://defuse.ca/race-conditions-in-web-applications.htm) y también en [Condición de Carrera](https://en.wikipedia.org/wiki/Race_condition)

En la entrada se comenta sobre varios fallos de sitios de alto nivel (que, al final, es lo que hace que valga la pena comentarlos aquí). Son secuencias de pasos para fallos de Facebook (en este caso aumentar el número de revisiones de una página o crear varios nombres de usuario para una cuenta), DigitalOcean (añadir crédito a nuestra cuenta), y LastPass (con un fallo parecido al de DigitalOcean).
