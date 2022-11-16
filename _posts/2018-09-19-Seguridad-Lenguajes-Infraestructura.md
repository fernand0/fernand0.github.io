---
layout: post
title: "Vulnerabilidades en los lenguajes que nos permiten desarrollar programas"
date: "Wed Sep 19 16:02:01 +0100 2018"
category: seguridad
tags: [seguridad, vulnerabilidades, fuzzing, fallos, bugs, lenguajes, intérpretes]
imagefeature: https://c2.staticflickr.com/6/5015/5494861863_8a8743b4c9_m.jpg
---


<a href="https://www.flickr.com/photos/fernand0/5494861863" title="Herramientas de construcción"><img src="https://c2.staticflickr.com/6/5015/5494861863_8a8743b4c9_m.jpg" width="240"  alt="Herramientas de construcción" style="float:left; margin:5px"></a>
Tenemos que tenerlo claro: construir un sistema informático seguro es difícil. Los fallos pueden venir de tantos sitios, incluso incontrolables por nosotros que siempre puede pasar algo (malo).
En este caso traemos [Secure Apps Exposed to Hacking via Flaws in Underlying Programming Languages](https://www.bleepingcomputer.com/news/security/secure-apps-exposed-to-hacking-via-flaws-in-underlying-programming-languages/) donde nos hablan de como aplicaron las técnicas de *Fuzzing* para identificar vulnerabilidades en intérpretes de diferentes lenguajes de programación.

Recordemos que el *fuzzing* consiste en proporcionar entradas inesperadas (simpelmente basura, muchas veces) a una interfaz para ver qué sucede. Muchas veces, cosas malas, que señalan diversos problemas.

> Fuzzing is an operation that involves providing invalid, unexpected, or random data as input to a software application. Fuzzing has been used for years in the software testing field but has recently become very popular with security researchers, especially with Google's security team and the Linux community.

En este caso se evaluaron intérpretes de JavaScript, Perl, PHP, Ruby y Python.

> The author of this research is IOActive Senior Security Consultant Fernando Arnaboldi. The expert says he used an automated software testing technique named fuzzing to identify vulnerabilities in the interpreters of five of today's most popular programming languages: JavaScript, Perl, PHP, Python, and Ruby.

Un resumen de los descubrimientos:

- Python contiene métodos no documentados y variables de entorno que pueden utilizarse para ejecutar instrucciones del sistema operativo.
- Perl incluye una función *typemaps* que permite la ejecución de código similar a *eval()*
- NodeJS muestra mensajes de error que divulgan parcialmente el contenido de ficheros.
- JRuby carga y ejecuta código remoto en funciones que no deberían permitirlo.
- Los nombres de constantes de PHP permitirían ejecutar instrucciones de manera remota.

> ➣ Python contains undocumented methods and local environment variables that can be used for OS command execution.

> ➣ Perl contains a typemaps function that can execute code like  eval().

> ➣ NodeJS outputs error messages that can disclose partial file contents.

> ➣ JRuby loads and executes remote code on a function not designed for remote code execution.

> ➣ PHP constant's names can be used to perform remote command execution. 

El artículo es de hace un par de años así que estos fallos se habrán solucionado. Pero da miedo.
