---
layout: post
title: "Seguridad de las contraseñas: los sitios y lo que se sabe"
date: "2023-12-13 15:00:00 +0000"
category: seguridad
tags:
- seguridad
- artículo
- investigación
- research
- paper
- contraseñas
- passwords
imagefeature: 'https://i.imgur.com/ayQ8ioV.png'
---
<blockquote class="imgur-embed-pub" lang="en" data-id="ayQ8ioV"><a href="https://imgur.com/ayQ8ioV">View post on imgur.com</a></blockquote><script async src="//s.imgur.com/min/embed.js" charset="utf-8"></script>

Después de la calurosa recepción de los comentarios sobre artículos de investigación (es broma, creo que podría escribir al revés aquí y nadie diría nada) traemos otro que me resultó intersante: <a href="https://www.usenix.org/conference/soups2022/presentation/lee">Password policies of most top websites fail to follow best practices</a>.

Y es intersante, porque con todo lo que vamos sabiendo sobre las contraseñas, muchos sitios siguen usando políticas viejas, anticuadas y hasta desaconsejadas.

En el resumen nos dicen:

> We examined the policies of 120 of the most popular websites for when a user creates a new password for their account. Despite well-established advice that has emerged from the research community, we found that only 13% of websites followed all relevant best practices in their password policies. Specifically, 75% of websites do not stop users from choosing the most common passwords—like "abc123456" and "P@$$w0rd", while 45% burden users by requiring specific character classes in their passwords for minimal security benefit. We found low adoption of password strength meters—a widely touted intervention to encourage stronger passwords, appearing on only 19% of websites. Even among those sites, we found nearly half misusing them to steer users to include certain character classes, and not for their intended purpose of encouraging freely-constructed strong passwords.

De las buenas prácticas que se recomiendan habitualmente, nos dicen:

* La recomendación: Comprobar las contraseñas contra listas divulgadas y otras que son fáciles de adivinar.

El resultado: 71 de 120 sitios no comprueban la contraseña en absoluto, permitiendo 40 de las más frecuentes. 

* La recomendación. Rechazar la contraseña si aparece en alguna de estas listas. 
El resultado: De los que las comprueban, 19 bloquean menos de la mitad de las listas de contraseñas comunes.

* La recomendación: proporcionar información en tiempo real sobre la estimación de complejidad de las contraseñas.

El resultado: Sólo 23 de los 120 sitios comprobados tenían medidor de la calidad.

* La recomendación: establecer un requisito de dificultad mínima mediante estimaciones de la 'adivinabilidad' de la clave.

El resultado: de los 23 anteriores, 10 utilizan medidores basados en el tipo de caracteres que se utililiza, sin prestar atención a nada más.

* La recomendación: no exigir clases especiales de caracteres; permitir a los usuarios construir sus contraseñas libremente.

El resultado: 54 de 120 sitios exigen el cumplimiento de reglas sobre los caracteres.

* La recomendación: establecer un mímino de al menos 8 caracteres (NIST).

El resultado: 66 de los 120 sitios exigen esa longitud, al menos.

Las conclusiones son:

* La política de contraseñas es teatro de seguridad (*security theater*)
* Los sitios han preferido pasar a otros métodos (como autentificación multifactor) para aliviar los problemas (con sus propias dificultades/debilidades).
* Los sitios necesitan pasar auditorías de seguridad, pero estas auditorías recomiendan a veces prácticas obsoletas.
* Los sitios tienen otras restricciones que tal vez expliquen estas malas prácticas.


Se puede descargar el artículo en <a rhef="https://www.usenix.org/system/files/soups2022-lee.pdf">[PDF] Password policies of most top websites fail to follow best practices</a>, la <a href="https://www.usenix.org/system/files/soups2022_slides_lee.pdf">[PDF] presentación de Password policies of most top websites fail to follow best practices</a> y ver el vídeo en <a href="https://youtu.be/yHYEBbXOenI">Password policies of most top websites fail to follow best practices</a>.
