--- 
layout: post
title: "Las herramientas sencillas también nos pueden ayudar a encontrar problemas de seguridad"
date: "Tue Dec 17 15:05:01 +0100 2019"
category: seguridad
tags: [desarrollo, bugs, fallos, errores, seguridad, grep, búsqueda]
imagefeature: https://live.staticflickr.com/6137/5941906171_2d4ac80c32_m.jpg
---

<a href="https://www.flickr.com/photos/fernand0/5941906171" title="Un fallo cualquiera"><img src="https://live.staticflickr.com/6137/5941906171_2d4ac80c32_m.jpg" width="240"  alt="Un fallo cualquiera" style="float:left; margin:5px"></a>
Cuando yo empecé a interesarme por el desarrollo seguro de aplicaciones las únicas herramientas que había eran buscadores de cadenas más o menos potentes; estas herramientas no podían 'comprender' el flujo del código ni hacer seguimiento de las variables (lo más parecido a eso era el [Taint mode de Perl](https://perldoc.perl.org/perlsec.html#Taint-mode). Posteriormente las herramientas han ido mejorando (y encareciéndose) y ahora son capaces de cosas mucho más interesantes.

Sin embargo, la búsqueda de patrones sigue siendo una herramienta más y de eso habla [Don’t Underestimate Grep Based Code Scanning](https://littlemaninmyhead.wordpress.com/2019/08/04/dont-underestimate-grep-based-code-scanning/) que empieza hablando de las herramientas y cómo el mercado está copado por unos pocos fabricantes de herramientas bastante caras:

> The SAST market is dominated by a small number of big players that charge high licencing fees for tools that do sophisticated analysis. One of the main features of such tools is the data flow analysis, which traces vulnerabilities from source to sink, potentially going across a number of files.

Sigue habiendo herramientas más sencillas (y económicas) que también son más eficientes:

> There are lower cost, more efficient SAST tools, but they typically do lack the sophistication in terms of quality of security bug findings. Perhaps the most popular low-cost alternative is SonarQube,...

A pesar de todo, como decíamos, se puede usar la búsqueda de patrones (la herramienta prototípica sería *grep*):

> In this blog, we’re going to talk about grep-based code scanning, which is an old fashioned way of SAST scanning — but we argue that good grep based scanning can do reasonably well compared to expensive SAST tools in terms of quality of bugs found. 

Y después hace unas cuantas consideraciones para pasar a indicarnos qué buscar, con cadenas como: "password, passwd, credential, passphrase", o "sql, query(". Sin olvidar las funciones inseguras como "strcat, strcpy, strncat, strncpy, sprintf, gets" y otras muchas cadenas que pueden darnos indicios de que algo puede que no vaya bien del todo. O, al menos, que tal vez deberíamos mirar allí.

Curioso.
