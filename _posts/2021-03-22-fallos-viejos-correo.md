---
layout: post
title: El correo y su realidad a través de las implementaciones
date: 2021-03-22 15:00:00 +0000
category: seguridad
tags:
- seguridad
- correo
- mail
- protocolos
- implementación
imagefeature: 'http://live.staticflickr.com/65535/48737698728_25b68180f2.jpg'

---
<a href="https://www.flickr.com/photos/fernand0/48737698728/" title="Portada Real Casa de Correos "><img src="http://live.staticflickr.com/65535/48737698728_25b68180f2.jpg" alt="Portada Real Casa de Correos " width="240" style="float:left; margin:5px"></a>
El correo electrónico es una de las aplicaciones más viejas de internet. Además es una de las pocas que se ha mantenido verdaderamente descentralizada: es cierto que hay una cierta tendencia al uso de los proveedores habituales, pero sigue habiendo muchos servidores de correo 'independientes' y con los que todo el mundo tiene que poder interactuar.

Esto provoca que haya algunos problemas de seguridad (y el spam, claro). En [Decades-Old Email Flaws Could Let Attackers Mask Their Identities](Decades-Old Email Flaws Could Let Attackers Mask Their Identities) hablan del tema, centrándose en algunos de los sistemas que se han añadido para hacer que el correo sea más seguro y confiable.
En particular, el marco de política de envíos, el correo identificado mediante claves de dominios y la autentificación basada en dominios.

> The study looked at the big three protocols used in email sender authentication—Sender Policy Framework (SPF), Domain Keys Identified Mail (DKIM), and Domain-Based Message Authentication, Reporting and Conformance (DMARC)—and found 18 instances of what the researchers call "evasion exploits." 

Nos dicen que el problema no está en los protocolos, sino en cómo los implantan diferentes servicios.

> The vulnerabilities don't stem from the protocols themselves but from how different email services and client applications implement them. Attackers could use these loopholes to make spear-phishing attacks even harder to detect.

Hay ataques dentro del servidor, basados en inconsistencias sobre como un servicio obtiene los datos de las cabeceras para autentificar a un usuario.

>  The first set, called "intra-server" attacks, prey on inconsistencies in how a given email service pulls data from headers to authenticate a sender. 

El segundo se basa en manipular inconsistencias similares, pero entre el servidor que recibe el mensaje y la aplicación que usamos para leerlo.

> The second category focuses on manipulating similar inconsistencies, but between the mail server that receives your message and the app that actually displays it to you. 

Finalmente, las 'respuestas ambiguas' por problemas en cómo se manejan algunas cabeceras de autentificación.

> The researchers call the third category "ambiguous replay," because it includes different methods of hijacking and repurposing (or replaying) a legitimate email an attacker has received. These attacks take advantage of a known quality of the cryptographic authentication mechanism DKIM where you can receive an email that has already been authenticated, craft a new message where all of the headers and the body are the same as they were in the original email, and essentially resend it, preserving its authentication. 

Todos estos problemas abren la puerta a poder enviar sin demasiados problemas toda clase de basura, en muchos casos porque los proveedores se mueven buscando la compatibilidad, más que el rigor. Sin darse cuenta de la existencia de esos casos límite, que serán explotados por alguien  para seguir abusando de los sistemas de correo.


