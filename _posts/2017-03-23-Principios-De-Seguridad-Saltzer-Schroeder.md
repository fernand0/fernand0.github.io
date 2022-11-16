---
layout: post
title: "Principios de seguridad de Saltzer y Schroeder"
date: "Thu Mar 23 17:10:01 +0100 2017"
category: seguridad
tags: [seguridad, principios, diseño]
imagefeature: https://c2.staticflickr.com/4/3668/10389877603_d73d54a85b_m.jpg
---




<a href="https://www.flickr.com/photos/fernand0/10389877603" title="C3PO"><img src="https://c2.staticflickr.com/4/3668/10389877603_d73d54a85b_m.jpg" width="240"  alt="C3PO" style="float:left; margin:5px"></a>
Muchas veces se utiliza la palabra principios como algo grandilocuente y altisonante para justificar casi cualquier cosa. En el contexto de seguridad (y seguramente en la vida también) los principios deberían ser normas o reglas de caracter general que nos permiten tomar decisiones y actuar cuando no tenemos otras normas más claras y directas. Serían las que nos permiten pensar en los problemas de los que todavía no somos conscientes, o afrontar los que ya conocemos pero para los que hemos de adoptar una aproximación más o menos consistente.

En este caso tenemos [The Security Principles of Saltzer and Schroeder](http://emergentchaos.com/the-security-principles-of-saltzer-and-schroeder). 

> This kind of arrangement is accomplished by providing, at the higher level, a list-oriented guard whose only purpose is to hand out temporary tickets which the lower level (ticket-oriented) guards will honor

Los principios serían:

* Economía del mecanismo. Esto es, mantener el sistema tan pequeño y simple comoo sea posible.
* Por defecto, fallar de forma segura. Basar las decisiones sobre acceso en lo que está permitido, en lugar de lo que está prohibido. De esta forma, si algo no está permitido por error es mejor (desde el punto de vista de la seguridad) que si está incorrectamente admitido.
* Mediación completa. Esto es, siempre comprobar la autorización antes de conceder el derecho. 
* Mínimo privilegio. Tener permiso exclusivamente para hacer lo que necestia nuestro trabajo.
* Mínimo común mecanimo. Minimizar la cantidad de información y otros artefactos compartidas entre diferentes usuarios o de la que dependen muchos usuarios.
* Separación de privilegios. Cuando sea posible, un mecanismo de protección que necesita dos claves es más robusto y flexible que uno que sólo requiera una.
* Diseño abierto. El diseño no puede ser secreto y la protección no debería basarse en el desconocimiento del atancante.
* Sicológicamente aceptable. Si lo que se propone no entra en nuestros esquemas mentales puede que lo aceptemos, pero terminaremos tratando de saltarlas, aligerarlas o evitarlas.

Vale la pena leer el artículo porque utiliza ejemplso de la saga de películas de Star Wars.

Y vale la pena recordar los principios para cuando tengamos dudas sobre cómo realizar alguna tarea para la que no tenemos las reglas claras del todo.
