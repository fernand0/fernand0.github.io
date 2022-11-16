--- 
layout: post
title: "Los consejos, a veces, son como las opiniones"
date: "Tue Mar 21 15:05:01 +0100 2019"
category: seguridad
tags: [seguridad, consejos, ejemplos, errores, stack overflow]
imagefeature: https://farm5.staticflickr.com/4242/35793305495_e45e53e36f_m.jpg
---



<a href="https://avecesunafoto.wordpress.com/2019/02/12/papeleo/" title="Cantidad y no calidad"><img src="https://avecesunafoto.files.wordpress.com/2019/02/img_20190111_134801.jpg" width="240"  alt="Cantidad y no calidad" style="float:left; margin:5px"></a>
Este es otro de los temas recurrentes en este sitio es los errores que se transmiten a modo de ejemplos, ayudas y otros mecanismos que los programadores utilizan para resolver sus dudas. Hace algún tiempo lo comentamos en [Seguir la corriente resolviendo problemas y la seguridad](https://fernand0.github.io/Cuidado-Con-Los-Ejemplos/) y el tema volvió a principios de este año con una nueva investigación. 
Nos lo contaban en [Popular coding advice doesn’t necessarily equal secure coding advice](https://www.helpnetsecurity.com/2019/01/09/insecure-coding-advice/) y hablan de una investigación más reciente:

> According to more recent research by a group of researchers from Virginia Tech, TU Munich and the University of Texas at San Antonio, the answer is “no.”

cuando se preguntan si estos foros ayudan a diferenciar elecciones seguras frente a las inseguras.

El estudio lo realizarn en el sitio Stack Overflow buscando contenido relacionado con la seguridad, en particular seguridad en Java.

> The researchers conducted a study on security-related Stack Overflow posts and contrasted secure and insecure advice with the community-given content evaluation. To ensure a fair comparison between secure and insecure suggestions, they focused on the discussion threads related to Java security.

Stack Overflow es un sitio muy conocido entre los programadores e informáticos en general y, además, están orgullosos de hacer un seguimiento de las respuestas para evitar repeticiones, imprecisiones, y otros defectos de sitios donde cualquiera puede responder. Sin embargo, no parecen muy eficaces aclarando temas con la seguridad en mente:

> “Compared with secure suggestions, insecure ones had higher view counts (36,508 vs. 18,713), received a higher score (14 vs. 5), and had significantly more duplicates (3.8 vs. 3.0) on average. 34% of the posts provided by highly reputable so-called trusted users were insecure.”

Esto es, los mecanismos que tiene el sitio para mejorar la seguridad no funcionan bien a la hora de identificar respuestas confiables.

> Also, its reputation mechanism fails to point out trustworthy users with respect to security questions.

Muy interesante.
