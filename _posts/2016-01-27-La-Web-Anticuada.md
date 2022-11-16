---
layout: post
title: ".es, la web anticuada"
date: "Wed Jan 27 11:35:01 +0100 2016"
category: seguridad
tags: [seguridad, web, .es, análisis, demoscopia, demoscopía, internet, versiones, anticuado]
---





<a href="https://www.flickr.com/photos/fernand0/20046312" title="Respuesta servidor"><img src="https://c1.staticflickr.com/1/15/20046312_b51813014d_m.jpg" width="240"  alt="Respuesta servidor" style="float:left; margin:5px"></a>
Una de las formas que tenemos hoy en día de averiguar como es el mundo es preguntando a la web. Se trata de desargar y analizar la información (meta-información) disponible en internet que nos puede dar pistas sobre las organizaciones en distintos ámbitos. De ello hablábamos el otro día en [Alguien puede estar tratando de conocerte mejor](http://fernand0.github.io/Escaneando-Redes-Obteniendo-Informacion/) pero hemos hablado más veces antes: [demoscopía](https://mbpfernand0.wordpress.com/tag/demoscopia/).

Hoy vamos a hablar un poquito de los servidores web en los dominios .es. En [Análisis de servidores web en dominios ".es" (I)](http://www.securityartwork.es/2015/06/26/analisis-de-servidores-web-en-dominios-es-i/) Luis Martín lanzaba un análisis a los servidores web de los dominios .es para determinar qué servidores se estaban utilizando, versiones, sistemas operativos y esas cosas. La conclusión es que el servidor mayoritario es Apache, seguido del IIS. En ambos casos, versiones no muy recientes:

> Apaches con más de un año de antigüedad: 109715.
> Apaches con menos de un año de antigüedad: 37714.

Y también:

> 8799 dominios usarian IIS actualizados.
> 105926 usan IIS antiguos y potencialmente vulnerables.

Naturalmente, dada la naturaleza de estos datos esto no significa que todos sean vulnerables (incluso podrían estar proporcionandodatos falsos). Pero muy buena impresión no da.

El análisis continuaba con [Análisis de servidores web en dominios ".es" (II)](http://www.securityartwork.es/2015/07/01/analisis-de-servidores-web-en-dominios-es-ii/), donde se analizan los lenguajes y sistemas de gestión de contenidos utilizados en estas páginas web. Los más populares parecen ser PHP y ASP.NET.

Nuevamente no parece que la actualización sea una de las prioridades de la web española.

Insisto, no hay que tomar como palabra de ley estos datos, pero a mi me dejan un poco preocupado, la verdad:

> Hemos de tener en cuenta que este estudio ha sido realizado de manera muy superficial, cuidando hasta el extremo el potencial impacto y siendo lo menos agresivos posible. Toda la información obtenida está “ahí fuera” sin necesidad de “rascar”, disponible para todo el mundo incluidos aquellos sin buenas intenciones. Seguramente un enfoque más profundo (sin necesidad de ser agresivo) proporcionaría mucha más información del estado actual de servicios Joomla!, WordPress, IIS o Apache.
