---
layout: post
title: "¿En qué confíamos?"
date: "Wed Dec 19 23:40:01 +0100 2014"
category: seguridad
tags: seguridad confianza trust 
imagefeature: https://drscdn.500px.org/photo/66381679/m=900_k=1_a=1/26576f61fae821c9aaa1b71f0019d930
---

En [Un compilador que infecta los binarios](http://mbpfernand0.wordpress.com/2009/09/01/un-compilador-que-infecta-los-binarios/) hablábamos de la confianza y recuperábamos una lectura clásica sobre el tema de en qué podemos confiar y cómo en algún momento cedemos el control.

Se me había pasado la técnica que propuso [David A. Wheeler’s Page on Fully Countering Trusting Trust through Diverse Double-Compiling (DDC) - Countering Trojan Horse attacks on Compilers](http://www.dwheeler.com/trusting-trust/) donde habla de cómo se podría mejorar la confianza en los binarios que generemos, mediante doble compilación diversificada, "Diverse Double-Compiling” (DDC). En el resumen:

> In the DDC technique, source code is compiled twice: once with a second (trusted) compiler (using the source code of the compiler’s parent), and then the compiler source code is compiled using the result of the first compilation. If the result is bit-for-bit identical with the untrusted executable, then the source code accurately represents the executable. 

Hay un [vídeo sobre la PhD Public Defense of Fully Countering Trusting Trust through Diverse Double-Compiling](http://www.dwheeler.com/trusting-trust/dissertation/wheeler-trusting-trust-video.html)

Hay esperanza. Pero ... ¿Estamos dispuestos a pagar el precio de la complejidad añadida?
