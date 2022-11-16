---
layout: post
title: "Correo para la gestión de accesos"
date: "Tue Apr 12 10:00:01 +0100 2016"
category: seguridad
tags: [seguridad, contraseñas, claves, passwords, correo, gestión, recuperación]
---





<a href="https://www.flickr.com/photos/fernand0/5523743237" title="Asignando identificadores"><img src="https://c2.staticflickr.com/6/5060/5523743237_4282d2fcac_m.jpg" width="240"  alt="Asignando identificadores" style="float:left; margin:5px"></a>
Traigo hoy un par de referencias sobre algo que muchas veces ya estamos haciendo los usuarios en la práctica (y que algunos proveedores han 'estandarizado' más o menos en lo que denominan sistemas de acceso sin clave): cuando no recordamos la contraseña utilizamos el botón de recordarla y accedemos al sitio. Posteriormente, si no es un sitio que visitamos con frecuencia la olvidamos y la próxima evez seguiremos el mismo procedimiento.

En este caso lo contaban en [How to Fix Authentication: Email as a Password Manager](http://sakurity.com/blog/2015/04/10/email_password_manager.html). En este caso proponen que este sea el método de acceso y, por lo tanto, proponen que la contraseña remitida sea de un sólo uso. Las ventajas: no hacen falta aplicaciones extra, no hay problemas de sincronización (aunque a veces sabemos que los correos se 'atascan' o no podemos acceder a ellos de forma temporal), simple para los desarrolladores (al final los protocolos de recuperación de contraseña tienen su complejidad, recordemos [Introducing the “Secure Account Management Fundamentals” course on Pluralsight](http://fernand0.github.io/Fundamentos-De-Gestion-De-Cuentas/)), el registro y la entrada son iguales (con matices, supongo, por la cuestión de si estás ya registrado con una cuenta de correo diferente), sólo es necesario un click, podemos controlar la duración de la validez del enlace, y no necesitamos almacenar constraseñas (y, por lo tanto, no nos las pueden robar).
No termino de estar de acuerdo con la 'ventaja' de evitar el Facebook Connect (y similares) salvo por evitar su complejidad. Y tampoco con que no se puede aplicar fuerza bruta: obviamente se puede, aunque nosotros ahora tenemos más control sobre la dificultad de encontrar los enlaces, frente a las contraseñas que los usuarios suelen elegir de manera inadecuada. 

Como inconveniente, está claro que trasladamos toda la seguridad de nuestro sistema al proveedor de correo y a la gestión que el usuario haga de él.
Hay más, claro, nunca nada es tan fácil como creemos al principio.

No habría que olvidar la vigilancia de las cuentas gestionadas de esta manera (observación de anomalías, cambios, novedades,...) que también parece ser una de las tendencias en seguridad de cuentas hoy en día.

En [History of Email-Only Auth](https://medium.com/@lucas_gonze/history-of-email-only-auth-6b33b0065f74) hay más información y opiniones de diversas personas sobre ideas similares.
