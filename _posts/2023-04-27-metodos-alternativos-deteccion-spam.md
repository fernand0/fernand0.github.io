---
layout: post
title: "Métodos alternativos de detección de bots"
date: "2023-04-27 15:00:00 +0000"
category: seguridad
tags:
- seguridad
- fraude
- correo
- direcciones
- HIBP
imagefeature: 'https://live.staticflickr.com/2022/2047108638_89b9686898.jpg'
---
<a href="https://www.flickr.com/photos/fernand0/2047108638/" title="Robot "><img src="https://live.staticflickr.com/2022/2047108638_89b9686898.jpg" alt="Robot " class="img-responsive img-centered"></a>

A veces las ideas más simples son las más útiles.
En [Pwned or Bot](https://www.troyhunt.com/pwned-or-bot/) Troy Hunt nos contaba omo su base de datos de cuentas robadas puede servir para detectar usuarios leg´timos: si tu correo nunca ha aparecido en un volvado de datos de algún problema de seguridad de una empresa, es bastante probable que no sea legítimo, o que haya sido creado recientemente para tratar de engañar a alguien.

> If an email address hasn't been seen in a data breach before, it may be a newly created one especially for the purpose of gaming your system. 

Está claro que el argumento tiene fallos: puedes tener tu correo muy bien protegido, o ser un usuario nuevo que lo ha creado recientemente, ... No estar en uno de esos listados es un indicio, pero no garantiza nada.

> Absence of an email address in HIBP is not evidence of possible fraud, that's merely one possible explanation.

Por el contrario, si un correo está en alguna de las divulgaciones de datos robdos en el pasado, podemos decir con un nivel de confianza alto, que es un correo legítimo.

> However, if an email address has been seen in a data breach before, we can say with a high degree of confidence that it did indeed exist at the time of that breach.

Al final, claro, no se trata de un indicador perfecto, sino un elemento más a la hora de evaluar la probabilidad de que estemos ante una dirección de correo más o menos falsa, que trata de abusar de nuestro servicio.

> Think of breach history not as a binary proposition indicating the legitimacy of an email address, rather as one of assessing risk and considering "pwned or bot" as one of many factors

Curioso.
