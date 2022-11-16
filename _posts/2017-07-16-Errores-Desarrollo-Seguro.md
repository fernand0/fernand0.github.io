---
layout: post
title: "Algunos errores comunes tratando de arreglar problemas de 'Cross Site Scripting'"
date: "Sun Jul 16 16:45:01 +0100 2017"
category: programación
tags: [seguridad, xss, cross site scripting, programación, errores, fallos]
imagefeature: https://c1.staticflickr.com/3/2017/2446156740_3fa2f0f5b6_m.jpg
---




El 'cross site scripting' es un fallo frecuente en desarrollo web que consiste en permitir a los usuarios inyectar código ejecutable (típicamente javascript pero también otros) en páginas que pueden ver y utilizar otros usuarios. De esta forma los atacantes pueden robar información, saltarse algunos sistemas de control de acceso...

<a href="https://www.flickr.com/photos/fernand0/2446156740" title="Cruce roto"><img src="https://c1.staticflickr.com/3/2017/2446156740_3fa2f0f5b6_m.jpg" width="240"  alt="Cruce roto" style="float:left; margin:5px"></a>

En [Secure Coding 101: 4 Common Mistakes Developers Make When Fixing Cross-Site Scripting](https://www.vantagepoint.sg/blog/46-secure-coding-101-4-common-mistakes-developers-make-when-fixing-cross-site-scripting) nos recuerdan cuatro errores frecuentes:

* Utilizar listas negras. Por largas y completas que sean siempre será posible que algún atacante encuentre una forma de saltárselas. En seguridad informática siempre que sea posible hay que concentrarse en permitir lo que está bien, y no en prohibir lo que está mal.
* Aplicar filtros en lugar de 'escapar' la salida. Es muy difícil filtrar correctamente todos los caracteres necesarios en una aplicación normal, es mucho mejor aplicar códigos que evitan que determinados caracteres sean interpretados como caracteres de control (comillas, metacaracteres, ...).
* 'Escapar' los caracteres de forma inconsistente. Cuando utilizamos esta técnica, hay que hacerlo siempre y en todas las partes de nuestro programa. No sólo para evitar algún problema que ya hemos encontrado (o nos han encontrado).
* 'Escapar' los caracteres que no son. A pesar de que es una solución recomendada, tampoco es trivial de realizar. Por ejemplo, ¿qué sucedería si tus cadenas de texto que han sido tratadas de manera individual son concatenadas después?
