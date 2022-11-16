---
layout: post
title: Abusando de los clientes de correo
date: 2021-03-08 15:00:00 +0000
category: seguridad
tags:
- seguridad
- correo
- email
- clientes
- mailto
imagefeature: 'https://live.staticflickr.com/3782/11409966303_6d5aba8dcc.jpg'

---
<a href="https://www.flickr.com/photos/fernand0/11409966303/" title="Máquina "><img src="https://live.staticflickr.com/3782/11409966303_6d5aba8dcc.jpg" alt="Máquina " width="240" style="float:left; margin:5px"></a>
En seguridad informática los ataques pueden venir de las formas más insospechadas (incluso aunque estemos atentos). En este caso traigo [Some email clients are vulnerable to attacks via 'mailto' links](https://www.zdnet.com/article/some-email-clients-are-vulnerable-to-attacks-via-mailto-links/) donde nos cuentan un fallo utilizando enlaces del tipo `'mailto'` (esos enlaces, como sabemos, abren el cliente de correo con un destinatario preconfigurado).

> Mailto refer to special types of links, usually supported by web browsers or email clients. These are links that, when clicked, they open a new email compose/reply window rather than a new web page (website).

Como suele suceder, el estándar permite un montón de opciones, algunas incluso desaconsejadas por el mismo.

> However, even the standard itself warns software engineers against supporting all parameters, recommending that apps only support a few "safe" options.

Uno de ellos es el de añadir adjuntos (`'attach'`) que permiten que el destinatario esté precargado y, además, que el correo ya contenga un fichero adjunto.

> In particular, researchers looked at the mailto "attach" or "attachment" parameters that allow mailto links to open new email compose/reply windows with a file already attached.

Y, claro, como siempre decimos en las charlas divulgativas, lo que es fácil y rápido se consigue que de manera fácil y rápida alguien pueda fastidiarnos (por ejemplo, añadiendo nuestro fichero de claves, algún fichero de configuración....)

> If the user composing the email does not spot the file attachment, attackers could receive sensitive files from the user's system, such as encryption (PGP) keys, SSH keys, config files, cryptocurrency wallet files, password stores, or important business documents -- as long as they're stored at file paths known by an attacker.

También hablan de otro fallos de seguridad destinados a evitar las tecnologías de cifrado como, sustituir las claves, guardar información sensible en texto plano en sitios controlados por el atacante y divulgar las claves.

Cuidado.
