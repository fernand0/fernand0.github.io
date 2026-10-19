---
layout: post
title: "¿Cuánto tiempo tu dominio será tuyo?"
date: "2026-10-19 14:44:36 +0200"
category: seguridad
tags:
- seguridad
- dominios
- correo
- verificación
imagefeature: "https://live.staticflickr.com/65535/55409442529_21921d5c21_z.jpg"
---

<a data-flickr-embed="true" href="https://www.flickr.com/photos/fernand0/55409442529/" title="Jarras"><img src="https://live.staticflickr.com/65535/55409442529_21921d5c21_z.jpg" width="640" height="427" alt="Jarras"/></a><script async src="//embedr.flickr.com/assets/client-code.js" charset="utf-8"></script>

Muchas veces se habla de que corremos mucho riesgo al confiar nuestra presencia digital (y más, la comunicación digital, dirección de correo...) aservicios externos (gratuitos o no). La solución que suele proponerse es que vale la pena que contratemos nuestro propio dominio, ya que siempre podremos hacer que apunte a nuestro proveedor de cada momento.
El problema del que no se habla tanto es lo que puede suceder si perdemos ese dominio por cualquier motivo (dejamos de pagar, cambiamos a otro, ...).

En [Preventing Domain Resurrection Attacks](https://blog.pypi.org/posts/2025-08-18-preventing-domain-resurrections/) hablaban justamente de eso relacionado con el proyecto PyPI, que es un repositorio de proyectos escritos en Python y en el que muchos programadores confían.

El problema tiene que ver con el registro en el sitio, que va ligado a una dirección de correo.

> PyPI user accounts are linked to email addresses. Email addresses are tied to domain names; domain names can expire if unpaid, and someone else can purchase them.

Y el problema puede aparecer si el dominio de una de estas direcciones cambia de manos, el nuevo propietario podrá  usar las cuentas que considere oportuno, entre ellas alguna de las que existía anteriormente, asociada a algún proyecto.

> For older accounts prior to the 2FA requirement date, having an email address domain expire could lead to account takeover, which is what we're attempting to prevent, as well as minimize potential exposure if an email domain does expire and change hands, regardless of whether the account has 2FA enabled.

Para remediarlo, en PyPI hacen verificaciones sobre el estado de registro del dominio (dicho de forma muy simplificada) y cuando se produzca la caducidad considerarán las direcciones de correo asociadas como no verificadas.

> After an initial bulk check period that took place in April 2025, PyPI will check daily for any domains in use for status changes, and update its internal database with the most recent status.

El problema es que sólo agentes muy preocupados (y suficientemente grandes) pueden invertir recursos en este tipo de soluciones, así que veremos de vez en cuando cómo puede afectar esto en distintas situaciones.
