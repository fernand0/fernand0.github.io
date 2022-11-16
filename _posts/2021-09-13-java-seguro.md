---
layout: post
title: "¿Java es un lenguaje seguro?"
date: "2021-09-13 15:00:00 +0000"
category: seguridad
tags:
- seguridad
- desarrollo
- java
- lenguajes
imagefeature: 'https://live.staticflickr.com/176/399144526_e289577520.jpg'
---
<a href="https://www.flickr.com/photos/fernand0/399144526/" title="The pila seguridad "><img src="https://live.staticflickr.com/176/399144526_e289577520.jpg" alt="The pila seguridad " width="240" style="float:left; margin:5px"></a>
Cuando se habla de programación segura, suele decirse aquello de: 'utiliza un lenguaje que sea seguro' y, a veces, se pone como ejemplo Java (fundamentalmente por su gestión automática de la memoria, en contraposición con C; en este último la memoria se gestiona de manera manual por parte del programador).

En [No, Java is not a Secure Programming Language](https://littlemaninmyhead.wordpress.com/2021/01/28/no-java-is-not-a-secure-programming-language/) el autor argumenta que Java no es tan seguro como suele decirse.

En particular, nos cuenta, tiene muchos problemas debidos a los valores por defecto.

> Many Java security bugs are due to insecure defaults. As a consequence, developers need to have advanced development knowledge just to write simple code that cannot be easily exploited.

Y también porque la documentación no es muy buena.

> Java has really poor documentation: it is not hard to make things work, but it is often very unclear how to do things the ‘right way.’

Luego detalla el tratamiento de los diferentes problemas que aparecen en el OWASP Top 10, y con cuatro de ellos en particular: las entidades XML externas (XML External Entity), las vulnerabilidades de deserialización, los problemas de 'cross site scripting' y la exposición de datos delicados.

Posteriormente detalla otros problemas.

Lectura interesante.
