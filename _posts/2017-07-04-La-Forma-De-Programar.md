---
layout: post
title: "La forma de programar"
date: "Tue Jul 04 15:45:01 +0100 2017"
category: programación
tags: [programación, desarrollo, API, metodología, software, metodos]
imagefeature: https://c2.staticflickr.com/6/5053/5543692464_012820fbd6_m.jpg
---




Tengo mis dudas sobre el tema que traigo hoy aquí: porque soy culpable (cuando necesito hacer algo mínimamente complejo busco a ver si alguien ha hecho algo parecido y lo publicó para reutilizarlo). También porque me parece una buena práctica que favorece la economía, robustez...

<a href="https://www.flickr.com/photos/fernand0/5543692464" title="Viejo ordenador"><img src="https://c2.staticflickr.com/6/5053/5543692464_012820fbd6_m.jpg" width="240"  alt="Viejo ordenador" style="float:left; margin:5px"></a>

Sin embargo en [NPM & left-pad: Have We Forgotten How To Program? ](http://www.haneycodes.net/npm-left-pad-have-we-forgotten-how-to-program/) expone algunas quejas que pueden ser relevantes.

Dice que parece que el objetivo de la comunidad alrededor de NPM fuera escribir el mínimo código utilizando bibliotecas de otros para conseguir sus objetivos:

> It feels to me as if the entire job of an NPM-participating developer is writing the smallest amount of code possible to string existing library calls together in order to create something new that functions uniquely for their personal or business need.

Sin embargo, no hay ninguna garantía de que esas componentes estén bien (y lo vayan a estar en el futuro, si hay evoluciones de los sistemas):

> There’s absolutely no guarantee that what someone else has written is correct, or even works well.

De hecho, esta es una de las grandes prevenciones que se suelen contar en seguridad: no sólo tienes que estar seguro de que tu código es seguro, sino también el que utilices de terceros.

El último argumento que señalé es el de que, según el autor, juntar llamadas a APIs no se puede considerar programar y que puede convertirse en hacer cosas demasiado complejas:

> Finally, stringing APIs together and calling it programming doesn’t make it programming. It’s some crazy form of dependency hacking that involves the cloud, over-engineering things, and complexity far beyond what’s actually needed to create great applications.

Me parecen argumentos interesantes, pero que hay que manejar con cuidado: ni hayque volverse locos juntando piezas y creando auténticos 'Frankensteins'; ni tampoco hay que programar todo desde cero, gastando tiempo en desarrollar cosas que podríamos aprovechar para cubrir lo que es específico a nuestras necesidades.
