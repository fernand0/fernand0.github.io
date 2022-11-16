---
layout: post
title: "Evitar los 10 fallos de diseño más graves para la seguridad"
date: "Sun Nov 30 13:10:01 +0100 2014"
category: seguridad
tags: seguridad diseño flaws IEEE fallos
---

La IEEE lleva unos años fomentando la idea del desarrollo seguro. Una forma ha sido mediante la serie [Building Security In (IEEE Security & Privacy, Series Editor: Gary McGraw)](https://buildsecurityin.us-cert.gov/resources/building-security-in), bastante relacionada con el podcast de Gary McGraw [Silver Bullet](http://www.cigital.com/silver-bullet/).

Más recientemente han lanzado [The IEEE Computer Society Center for Secure
Design](http://cybersecurity.ieee.org/center-for-secure-design.html) y una
de sus primeras publicaciones ha sido [Avoiding the Top 10 Security
Flaws](http://cybersecurity.ieee.org/center-for-secure-design/avoiding-the-top-10-security-flaws.html).
Gary McGraw diferencia siempre que puede entre bugs (fallos de seguridad en
el código, fundamentalmente) y fallos de diseño (flaws).

En esa línea viene la lista, que ha desarrollado junto con otros autores:

- Gánala o concédela, pero nunca supongas la confianza.
- Utiliza mencanismos de autentificación que no puedan ser modificados ni evitados.
- Autorizar después de autentificar.
- Separar de manera estricta los datos del control. Nunca procesar instrucciones de control recibidas de fuentes no confiables.
- Definir una aproximación que asegure que todos los datos se validarán de manera explícita
- Utilizar correctamente la criptografía.
- Identificar los datos sensibles y cómo deberían manejarse.
- Siempre tener en cuenta a los usuarios.
- Comprender la forma en que cambia nuestra superficie de ataque la integración de componentes externas.
- Ser flexible cuando se consideren los cambios futuros de objetos y actores.

Algunas frases que señalé:

> various binary protection mechanisms can delay the leaking of sensitive material. 

Sobre autorización:

> Authorization should be conducted as an explicit check, and as necessary even after an initial authentication has been completed. Authorization depends not only on the privileges associated with an authenticated user, but also on the context of the request. 

Validación de datos:

>  Liberal use of precondition checks in the entry points of software modules and components is highly recommended.

Seguro que ustedes encuentran las suyas.
