--- 
layout: post
title: "Filtros de Bloom y optimización fallida"
date: "Mon Aug 31 15:02:01 +0100 2020"
category: desarrollo
tags: [desarrollo, optimización, algoritmia, algoritmos, filtros, perfilado]
imagefeature: http://live.staticflickr.com/65535/50287866366_cac584bcaa.jpg
---

<a href="https://www.flickr.com/photos/fernand0/50287866366/in/dateposted/" title="La tortuga como paradigma de la lentitud"><img src="http://live.staticflickr.com/65535/50287866366_cac584bcaa.jpg" alt="Tortuga y roca " width="240" style="float:left; margin:5px"></a>
Los filtros de Bloom son conocidos para comprobar si un elemento está en un conjunto de manera eficiente de manera probabilista; esto es, el filtro puede responder cosas como 'es posible que el elemento esté en el conjunto' o 'no está'. Se trata de obtener resultados cuando el conjunto de datos es tan grande que sería poco práctico utilizar otras técnicas más precisas.

En [When Bloom filters don't bloom](https://blog.cloudflare.com/when-bloom-filters-dont-bloom/) nos cuentan sobre su uso en la detección de falseamientos de la IP (*IP spoofing*) para tomar decisiones sobre ellos en [Cloudfare](https://cloudflare.com/).
El autor tenía un buen número de IPs recopiladas y al querer eliminar duplicados pensó que podrían servirle.

Nos cuenta detalles de sus desarrollos y la forma de hacerla más eficiente y como se encontró con un conjunto de datos que, aún así, no cabía en su memoria. Su programa invertía mucho tiempo moviendo datos entre las memorias disponibles.

Finalmente, indica algunas de las lecciones aprendidas:

El acceso a memoria secuencial y cuando se pueden predecir los siguientes accesos es algo que funciona bien en las CPUs modernas.

> Modern CPUs are really good at sequential memory access when it's possible to predict memory fetch patterns

Las estructuras de datos avanzadas son interesantes, pero hay que tener en cuenta el hardware y sus condicionantes (en este caso, las cachés).

> Advanced data structures are very interesting, but beware. Modern computers require cache-optimized algorithms. When working with large datasets, not fitting L3, ...

También algún comentario sobre el perfilado de programas.

Interesante.


[Bloom filter](https://en.wikipedia.org/wiki/Bloom_filter)
