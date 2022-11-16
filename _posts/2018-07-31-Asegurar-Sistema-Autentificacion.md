---
layout: post
title: "Cuatro ideas para asegurar la autentificación"
date: "Tue Jul 31 08:02:01 +0100 2018"
category: seguridad
tags: [seguridad, programación, autentificación, autenticación]
imagefeature: https://c1.staticflickr.com/3/2915/33534771015_707d3b9fb9_m.jpg
---


<a href="https://www.flickr.com/photos/fernand0/33534771015" title="Puerta"><img src="https://c1.staticflickr.com/3/2915/33534771015_707d3b9fb9_m.jpg" width="240"  alt="Puerta" style="float:left; margin:5px"></a>
El sistema de autentificación de los usuarios sigue siendo la única puerta de entrada a las caraterísticas de nuestro sistema que podamos ofrecerles.
Por este motivo, es una fuente segura de ataques, con diversas formas de intentar atacarnos para ver qué se puede conseguir.

En [4 Ways to Secure Your Authentication System in Rails](https://ducktypelabs.com/4-ways-to-secure-authentication/) hablan del tema para aplicaciones desarrolladas en Ruby on Rails, aunque las ideas se pueden aplicar en otros contextos.

Los consejos:

* Restringir las peticiones. 
Esto es, tratar de evitar los ataques de fuerza bruta, donde el 'malo' simplemente va probando diferentes identificadores y credenciales.

* Poner las cabeceras de seguridad correctamente.
Estar al día en las novedades y modificar nuestras aplicaciones no es un asunto trivial, pero tampoco es normal no aprovechar de las ventajas de unas cabeceras adecuadas (Recordatorio: [El uso de las cabeceras de los sitios web populares para aprender de seguridad](http://fernand0.github.io/Cabeceras-Seguridad-Sitios-Web-Populares/)).

* Leer bibliotecas de autentificación.
Leer el código de otros proyectos puede ayudarnos a hacer mejor las cosas nosotros. También el registro de cambios *changelog*
Da como ejemplo algunas características de algunas bibliotecas de las que se pueden aprender cosas interesanets (almacenamiento de hash de contraseñas separados y otros).

* Asegurar el resto de la aplicación.
Claro.
Da igual tener el mejor sistema de autentificación si pueden entrar por otro sitio. 
