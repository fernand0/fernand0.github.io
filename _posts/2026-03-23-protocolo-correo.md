---
layout: post
title: "IMAP: leyendo correos desde nuestra terminal"
date: "2026-03-23 14:00:00 +0000"
category: correo
tags:
- código
- correo
- IMAP
- protocolos
imagefeature: "https://live.staticflickr.com/2120/2442636467_4f8c7a19d8_z.jpg"
---

<a data-flickr-embed="true" href="https://www.flickr.com/photos/fernand0/2442636467/" title="Rimas populares"><img src="https://live.staticflickr.com/2120/2442636467_4f8c7a19d8_z.jpg" width="480" height="640" alt="Rimas populares"/></a><script async src="//embedr.flickr.com/assets/client-code.js" charset="utf-8"></script>

Suelo comentar siempre que puedo (y tiene sentido) cómo los protocolos de internet son bastante simples y, además, puro texto (que es algo que uno no siempre espera cuando lo que ve son imágenes, sonido, ...).

En [Talking To Your Mailserver Is Not as Hard as You Think!](https://blog.lohr.dev/imap-introduction) nos hablan del protocolo de correo IMAP (acceso remoto a carpetas en nuestro servidor) y cómo podemos 'hablar' con nuestro servidor de manera bastante sencilla.

Empieza recordándonos que se trata de un protocolo descentralizado.

> Unlike WhatsApp, Telegram or other messenger services, where the service provider has a centralized server (or nowadays a network of servers) processing all the messages; with emails, everybody can host their own mailserver to send and receive messages to everybody else.

IMAP son las siglas de protocolo de acceso a mensajes de internet y alrededor del correo electrónico es uno de los protocolos que hay, en este caso, para leerlo.

> IMAP, which stands for Internet Message Access Protocol.

Luego entra en detalles de las instrucciones ('comandos') necesarios para establecer una comunicación con nuestro servidor y poder interactuar para ver qué mensajes hay, leerlos, y realizar algunas operaciones.
No es la experiencia más amigable, pero nos dará una idea de todo lo que nuestro programa de correo hace por nosotros.
