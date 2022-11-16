---
layout: post
title: "El uso de algoritmos evolutivos en Facebook para buscar fallos"
date: "Thu Jun 07 16:02:01 +0100 2018"
category: fallos
tags: [fallos, bugs, facebook, algoritmos, evolutivos, pruebas, dinámicas]
imagefeature: https://c1.staticflickr.com/7/6137/5941906171_2d4ac80c32_m.jpg
---


<a href="https://www.flickr.com/photos/fernand0/5941906171" title="Fallo"><img src="https://c1.staticflickr.com/7/6137/5941906171_2d4ac80c32_m.jpg" width="240"  alt="Fallo" style="float:left; margin:5px"></a>
Hace mucho que no hablamos de algoritmos evolutivos y su utilización para buscar fallos. En [Facebook’s evolutionary search for crashing software bugs](https://arstechnica.com/information-technology/2017/08/facebook-dynamic-analysis-software-sapienz/) nos contaban como utilizan en Facebook estas ideas.

Cuando hacemos análisis de software hay fundamentalmente dos aproximaciones: análisis estático (recorremos el código buscando indicios de que algo puede ir mal) o dinámico (ejecutamos el programa con entradas diversas y vemos si falla).

En este segundo caso, el problema es encontrar entradas adecuadas. Ya hemos hablado del *fuzzing* (entradas aleatorias, para encontrar respuestas inesperadas o no suficientemente planificadas). Pero si estamos interesados en buscar fallos (y no simplemente esperar a ver si aparecen con pruebas aleatorias) puede ser interesante hacer pruebas con más 'intención'.

> There are a lot of dynamic analysers out there, but none like Sapienz, according to Facebook. The biggest problem with dynamic testing is finding the right inputs that cause an app to crash. 

Y aquí entran en juego los algoritmos evolutivos: orientar la búsqueda con parámetros adecuados para probar lo que nos pueda interesar más, que es encontrar fallos en el programa.

Como tiene que ser, el proyecto tiene información en [Sapienz: Intelligent automated software testing at scale](https://code.facebook.com/posts/134560877297803/sapienz-intelligent-automated-software-testing-at-scale/) y no dan muchos detalles, pero cuentan como el sistema es capaz de determinar entradas adecuadas para encontrar posibles fallos.

> Sapienz samples the space of all possible tests, using intelligent computational search and an approach called search-based software testing. An important design principle is that Sapienz tests through the UI, so issues Sapienz reports to engineers can be found through the UI. This avoids the false positives that bedevil many test design approaches, but it makes it more challenging to provide guidance to the computational search. 

Los algoritmos evolutivos, me permito recordar, nos permiten explorar espacios de búsqueda favoreciendo algunos tipos concretos de soluciones con un grado de efectividad bastante alto.
