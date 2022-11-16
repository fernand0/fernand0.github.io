--- 
layout: post
title: "Analizando vulnerabilidades por lenguajes"
date: "Tue Jul 09 15:05:01 +0100 2019"
category: seguridad
tags: [seguridad, lenguajes, análisis, vulnerabilidades, CVE]
imagefeature: https://live.staticflickr.com/176/399144526_e289577520_b.jpg
---


<a href="https://www.flickr.com/photos/fernand0/399144526" title="Seguridad en software"><img src="https://live.staticflickr.com/176/399144526_e289577520_b.jpg" width="240"  alt="Seguridad en software" style="float:left; margin:5px"></a>
Nos pongamos como nos pongamos, hay lenguajes de programación que nos facilitan más que otros el desarrollo de código seguro. Eso no significa que podamos utilizarlos y quedarnos tranquilos, pero si podemos elegir deberíamos tenerlo en cuenta.

En [The 3 least secure programming languages](https://www.techrepublic.com/article/the-3-least-secure-programming-languages/) nos contaban sobre un estudio que trataba de analizar este tema, con un estudio que analiza código disponible en diversos repositorios, sistemas de gestión de incidencias y los informes de vulnerabilidades de una de las bases de datos que se utilizan para estas cosas.
La noticia es bastante flojilla, pero si alguien está interesado en el informe se puede ver en [What Are The Most Secure Programming Languages](https://resources.whitesourcesoftware.com/research-reports/what-are-the-most-secure-programming-languages) pasando, eso sí, por un pequeño registro a su 'boletín'.

> ... the report compiled information from WhiteSource's database, which aggregates information on open source vulnerabilities from sources including the National Vulnerability Database (NVD), security advisories, GitHub issue trackers, and popular open source projects issue trackers. Researchers focused in on open source security vulnerabilities in the seven most widely-used languages of the past 10 years to learn which are most secure, and which vulnerability types are most common in each.

Los lenguajes más 'populares' cuando hablamos de vulnerabilidades por lenguaje serían:

> C (47%)
>
> PHP (17%)
>
> Java (11%)
>
> JavaScript (10%)
>
> Python (5%)
>
> C++ (5%)
>
> Ruby (4%)

Se refiere al número total de errores, así que la popularidad de un lenguaje influye (más usos, más errores).
En el informe lo aclaran, que es algo que no se hace en el artículo de prensa:

> For starters, more code has been written than any other language, providing more opportunities for vulnerabilities to be discovered. The fact is that C has been in use for much longer than most other languages, and is behind the core of most of the products and platforms we use. As such, it is bound to have more known vulnerabilities than the rest.

Las vulnerabilidades más frecuentes son el 'cross site scripting', validación de entradas, permisos, privilegios y control de acceso; finalmente divulgación de información.

Sin embargo, si leemos el informe, la imagen cambia un poco. En el año 2018, además del omnipresente C, Javascript, Java y PHP aparecen como fuente de errores de gravedad alta. Con números mucho más próximos entre sí.

Estos informes hay que leerlos siempre con un cierto escepticismo: malos desarrolladores harán mal código en cualquier lenguaje. Pero me parecen muy interesantes para conocer cómo está el mundo.
