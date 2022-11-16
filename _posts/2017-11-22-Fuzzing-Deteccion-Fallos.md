---
layout: post
title: "Fuzzing para detección de fallos en Google"
date: "Wed Nov 22 17:10:01 +0100 2017"
category: seguridad
tags: [seguridad, fuzzing, testing, pruebas, entrada, basura]
imagefeature: https://c2.staticflickr.com/8/7115/7616202138_9c37a542b3_m.jpg
---


<a href="https://www.flickr.com/photos/fernand0/7616202138" title="Líado"><img src="https://c2.staticflickr.com/8/7115/7616202138_9c37a542b3_m.jpg" width="240"  alt="Líado" style="float:left; margin:5px"></a>
Creo que hace un montón de tiempo que no hablábamos de `Fuzzing`: esencialmente (aunque últimamente se ha ido sofisticando) enviar basura diversa a las interfaces de entrada de los programas para detectar problemas de seguridad.

En [Announcing OSS-Fuzz: Continuous Fuzzing for Open Source Software](https://security.googleblog.com/2016/12/announcing-oss-fuzz-continuous-fuzzing.html) una iniciativa de Google para poner el sistema de fuzzing como servicio a disposición de desarrolladores de software libre. Ya ha servido para encontrar fallos en algunos proyectos:

> OSS-Fuzz has already found 150 bugs in several widely used open source projects (and churns ~4 trillion test cases a week). With your help, we can make fuzzing a standard part of open source development, and work with the broader community of developers and security testers to ensure that bugs in critical open source applications, libraries, and APIs are discovered and fixed. 

El proyecto está disponible en [oss-fuzz](https://github.com/google/oss-fuzz) con algo más de información.

Recordemos que Microsoft fue uno de los primeros promotores del fuzzing dentro de su ciclo de vida del desarrollo seguro (por cierto, más recientemente también ha puesto a disposición del público [Microsoft opens fuzz testing service to the wider public](https://www.helpnetsecurity.com/2017/07/28/microsoft-fuzz-testing-service/) y también que [Coverity Scan](https://scan.coverity.com/) es otro proyecto que ofrece sus servicios a los desarrolladores de software libre, desde otra perspectiva.
