---
layout: post
title: "Un caso real de un generador de contraseñas malas y cómo hacerlo bien"
date: "2022-01-31 15:00:00 +0000"
category: seguridad
tags:
- seguridad
- contraseñas
- claves
- PRNG
- generadores
imagefeature: 'https://live.staticflickr.com/65535/50633474928_a10b993b6d.jpg'
---
<a href="https://www.flickr.com/photos/fernand0/50633474928/" title="Generador "><img src="https://live.staticflickr.com/65535/50633474928_a10b993b6d.jpg" alt="Generador " width="240" style="float:left; margin:5px"></a>
Siempre recomendamos utilizar un gestor de contraseñas. Y aprovechar la función de generación de contraseñas. Generar buenas claves es un problema difícil, de todas formas, si nos fijamos en [Kaspersky Password Manager: All your passwords are belong to us](https://donjon.ledger.com/kaspersky-password-manager/). 

Allí nos cuentan algunos problemas que tenía su generador, que serán familiares para quien lea por aquí de vez en cuando:

* Utilizaban un generador de números aleatorios no criptográfico.
* La fuente de entropía era la hora (en segundos).

> The password generator included in Kaspersky Password Manager had several problems. The most critical one is that it used a PRNG not suited for cryptographic purposes. Its single source of entropy was the current time. All the passwords it created could be bruteforced in seconds.

El artículo explica cómo hacer un buen generador. Incluye código de ejemplo y buenos consejos, con la base en un caso real.
