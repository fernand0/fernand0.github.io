---
layout: post
title: Bugs con una larga historia. El caso de LZO
date: "Wed Apr 01 14:05:01 +0100 2015"
category: seguridad
tags: seguridad bugs lzo antiguo viejo ojos auditoria
---



<a href="https://www.flickr.com/photos/fernand0/2806340467/" title="Bicho"><img src="https://farm4.staticflickr.com/3285/2806340467_097b61ee10_m.jpg" width="240"  alt="Bugs"></a> 
En [Raising Lazarus - The 20 Year Old Bug that Went to Mars](http://blog.securitymouse.com/2014/06/raising-lazarus-20-year-old-bug-that.html) otra historia de esas que nos recuerda que hacer software seguro (o bien) es difícil. En este caso es una fallo sutil que ha escapado durante años a las revisiones que se hayan podido hacer (si es que se hicieron, que es otro de los temas que aparecen de vez en cuando relacionadas con el desarrollo de programas).

En esta ocasión se trata de diversos desbordamientos de enteros a la hora de ir almacenando valores y contabilizando el espacio que ocupan. 

En este caso, además, se añade el interés de que hay varias implementacionesd el algoritmo LZO (Lempel-Ziv-Oberhumer) que comparten algunas partes de su código.

Ya habíamos hablado de [El mito de los miles de ojos](https://mbpfernand0.wordpress.com/2009/09/07/el-mito-de-los-miles-de-ojos/) y más fallos con historial largo: [Un fallo de 17 años](https://mbpfernand0.wordpress.com/2010/05/06/un-fallo-de-17-anos/), [Alguien puso un troyano en mi servidor de IRC](https://mbpfernand0.wordpress.com/2010/06/24/alguien-puso-un-troyano-en-mi-servidor-de-irc/) y [Diaspora: lecciones de seguridad](https://mbpfernand0.wordpress.com/2010/10/04/diaspora-lecciones-de-seguridad/).
