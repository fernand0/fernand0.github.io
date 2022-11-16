---
layout: post
title: "Calidad del software y lenguajes de programación"
date: "Sun Feb 12 17:00:01 +0100 2017"
category: programación
tags: [programación, desarrollo, lenguajes, robustez, calidad, demoscopía]
imagefeature: https://c1.staticflickr.com/1/25/43497914_abb5dce40e_m.jpg
---





<a href="https://www.flickr.com/photos/fernand0/43497914" title="Verificación de programas"><img src="https://c1.staticflickr.com/1/25/43497914_abb5dce40e_m.jpg" width="240"  alt="Verificación de programas" style="float:left; margin:5px"></a>
En [[PDF] A Large Scale Study of Programming Languages and Code Quality in Github](http://macbeth.cs.ucdavis.edu/lang_study.pdf) nos muestran una investigación realizada examinando el código de los repositorios de GitHub: analizan para diversos tipos de lenguajes la cantidad de fallos, basándose en los 'commits' que contienen etiquetas relacionadas con errores ('error', 'bug', 'fix' , 'issue', 'mistake', 'incorrect', 'fault', 'defect' and 'flaw').

El resumen sería (de manera muy básica) que los lenguajes fuertemente tipados son algo mejores que los débilmente tipados. También que los lenguajes funcionales son algo mejores que los demás.

> ... we report that language design does have a significant, but modest effect on software quality. Most notably, it does appear that strong typing is modestly better than weak typing, and among functional languages, static typing is also somewhat bet- ter than dynamic typing. We also find that functional languages are somewhat better than procedural languages.

En todo caso, el efecto no es muy grande.

Puede que también tengan interés en leer los comentarios del hilo de Hacker News sobre el trabajo [A Large Scale Study of Programming Languages and Code Quality in GitHub](https://news.ycombinator.com/item?id=8558740).

También me gusta destacar el valor que tiene un sitio como GitHub (internet, para el caso) para poder realizar este tipo de estudios que serían bastante difíciles de realizar con el código disponible en 'casa' de cada uno que lo tenga.
