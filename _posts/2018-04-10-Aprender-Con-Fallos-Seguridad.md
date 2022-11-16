---
layout: post
title: "Aprender a programar con fallos de seguridad"
date: "Tue Apr 10 16:02:01 +0100 2018"
category: seguridad
tags: [seguridad, programación, ejemplos, tutoriales, código, copia, github]
imagefeature: https://farm3.staticflickr.com/2254/2234895945_ef79406f40_z.jpg 
---


<a href="https://www.flickr.com/photos/fernand0/2234895945/in/photolist-7pHZAc-4puqGH" title="En la pizarra"><img src="https://farm3.staticflickr.com/2254/2234895945_ef79406f40_z.jpg" width="240"  alt="En la pizarra" style="float:left; margin:5px"></a>
Lo leí en algún libro (creo que en el de John Viega y Gary McGraw, 'Building Secure Software'). Allí se decía que no sólo no se enseñaba el tema del desarrollo seguro sino que, además, los ejemplos que se podían ver en los libros de programación (en aquella época libros, fundamentalmente) eran de dudosa calidad desde el punto de vista de la seguridad. También se discutía (creo) sobre los ejemplos y sobre los ficheros de configuración. 
Desde entonces es un tema que suelo comentar (lo hice, por ejemplo, en la charla del otro día [Una charla sobre seguridad en aplicaciones web: principios y más](http://fernand0.github.io/Charla-Sobre-Desarrollo-Seguro/).
Casi 20 años después seguimos igual: en [Top-ranked programming Web tutorials introduce vulnerabilities into software](https://www.helpnetsecurity.com/2017/04/21/programming-tutorials-vulnerabilities/) nos dicen algo muy similar. Los tutoriales más importantes de desarrollo web incluyen ejemplos y soluciones vulnerables.

La forma de obtener el dato es curiosa: navegan por el repositorio GitHub y encuentran vulnerabilidades que pueden encontrarse en algunos textos introductorios disponibles por ahí.

> Researchers from several German universities have checked the PHP  codebases of over 64,000 projects on GitHub, and found 117 vulnerabilities that they believe have been introduced through the use of code from popular but insufficiently reviewed tutorials.

Utilizan la búsqueda en el repositorio de patrones bien conocidos de fallo, que se pueden encontrar en los tutoriales. Y encuentran problemas, claro:

> Thanks to our framework, we have uncovered over 100 vulnerabilities in web application code that bear a strong resemblance to vulnerable code patterns found in popular tutorials. More alarmingly, we have confirmed that 8 instances of a SQLi vulnerability present in different web applications are an outcome of code copied from a single vulnerable tutorial,” they noted. “Our results indicate that there is a substantial, if not causal, link between insecure tutorials and web application > vulnerabilities.”

Casi nada. En un caso concreto 8 ejemplos de un fallo que proviene de uno de estos tutoriales.

Proporcionan sus herramientas [GithubSpider](https://github.com/tommiu/GithubSpider) para hacer las búsquedas, y [ccdetection](https://github.com/tommiu/ccdetection) para hacer la detección de código similar.

Si haces cursos y tutoriales, o si ya tienes algunos publicados, tienes una responsabilidad.

También tengo que decir que hace años propuse algo así (cuando pensábamos en temas de propagación de información) relacionado con la propagación de errores en los programas a través de ejemplos, copia, etc. en una presentación que nunca llegué a publicar, así que pueden creerme o no sobre el tema.
