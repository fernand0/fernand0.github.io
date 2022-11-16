---
layout: post
title: "¿En quién confías? El compilador"
date: "Tue Sep 07 16:25:01 +0100 2016"
category: seguridad
tags: seguridad, confianza, trust, compilador, ataques, infección, troyanos
imagefeature: https://drscdn.500px.org/photo/66381679/m=900_k=1_a=1/26576f61fae821c9aaa1b71f0019d930
---



<a href="https://www.flickr.com/photos/fernand0/329254642" title="Mac de Apple"><img src="https://c1.staticflickr.com/1/152/329254642_451c5d85a6_m.jpg" width="240"  alt="Mac de Apple" style="float:left; margin:5px"></a>
Para mi es una lectura imprescindible el [[PDF] Reflections on Trusting Trust](http://www.ece.cmu.edu/%7Eganger/712.fall02/papers/p761-thompson.pdf) de Ken Thompson y ya hemos hablado del mismo tema en alguna ocasión, por ejemplo en [Un compilador que infecta los binarios](https://mbpfernand0.wordpress.com/2009/09/01/un-compilador-que-infecta-los-binarios/) donde aquellas ideas pasaban de la teoría a la práctica.

Más recientemente podíamos leer sobre XcodeGhost, que realizaba el ataque contra el compilador Xcode de Apple para iOS y OS X:

> XcodeGhost is an example of compiler malware. Instead of trying to create a malicious app and get it approved in the App Store, XcodeGhost’s creator(s) targeted Apple’s legitimate iOS/OSX app development tool called Xcode to distribute the malicious code in legitimate apps.

Los 'malos' habrían 'adaptado' el compilador para sus objetivos y habrían colgado el enlace en distintos foros para que la gente se lo bajase y lo utilizase, produciendo un buen número de infecciones en diversos programas que terminaron en la AppStore.

Nótese que es un problema muy fácil de evitar, simplemente bajándose las herramientas de sitios confiables y no escuchando los cantos de sirenas de los foros y sitios de noticias. Pero aún así, algunos desarrolladores cayeron e infectaron a sus usuarios.
