---
layout: post
title: "Fallos en el kernel de Linux"
date: "Mon Sep 11 16:02:01 +0100 2018"
category: programación
tags: [programación, fallos, bugs, kernel, linux, análisis]
imagefeature: https://c2.staticflickr.com/4/3028/2744387443_c9a664ff65_m.jpg
---


<a href="https://www.flickr.com/photos/fernand0/2744387443" title="Bicho"><img src="https://c2.staticflickr.com/4/3028/2744387443_c9a664ff65_m.jpg" width="240"  alt="Bicho" style="float:left; margin:5px"></a>
Con lo que sabemos hoy en día parece que es prácticamente imposible entregar un producto informático sin fallos (aunque hay quien dice que puede hacerlo bastante bien),
[System complexity, safety, security drive continued adoption of Ada, SPARK in aerospace and defense software engineering](https://www.intelligent-aerospace.com/articles/2018/05/system-complexity-safety-security-drive-continued-adoption-of-ada-spark-in-aerospace-and-defense.html)).

También nos gusta bastante la cantidad de cosas que se pueden aprender de los productos de código abierto, donde se puede mirar, medir y aprender ([Bitergia](https://bitergia.com/), por ejemplo, se dedica a eso).

Podíamos leer en [Static analysis on the Linux kernel](http://smackerelofopinion.blogspot.com/2017/09/static-analysis-on-linux-kernel.html) los resultados de diferentes mediciones realizadas sobre el kernel de Linux, principalmente los análisis que realiza la empresa [Coverity sobre diversos proyectos de software libre](https://scan.coverity.com/o/oss_success_stories). 
El resumen sería este:

> As one can see, there are a lot of defects getting fixed by the Linux developers and the overall trend of outstanding issues is downwards, which is good to see.  The defect rate in linux-next is currently 0.46 issues per 1000 lines (out of over 13 million lines that are being scanned). A typical defect rate for a project this size is 0.5 issues per 1000 lines.  Some of these issues are false positives or very minor / insignificant issues that will not cause any run time issues at all, so don't be too alarmed by the statistics

Esto es, en el Kernel de Linux tiene una tasa de defectos de 0.46 por cada mil líneas, teniendo en cuenta que es una prueba automatizada que detectará como fallos cosas que no lo son, y dejará de detectar otros.

