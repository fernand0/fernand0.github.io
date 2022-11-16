---
layout: post
title: "GitHub y sus cambios en los nuevos formatos de los tokens de autentificación"
date: "2021-11-29 15:00:00 +0000"
category: seguridad
tags:
- seguridad
- tokens
- github
- autorización
- autentificación
imagefeature: 'https://live.staticflickr.com/53/108132770_3d96ff2de5.jpg'
---
<a href="https://www.flickr.com/photos/fernand0/108132770/" title="Más bolas "><img src="https://live.staticflickr.com/53/108132770_3d96ff2de5.jpg" alt="Más bolas " width="240" style="float:left; margin:5px"></a>
A veces, cuando diseñamos un sistema, no somos conscientes de todas las consecuencias de nuestras decisiones. Tarde o temprano nos tocará cambiar algunas partes para remediar estos problemas. En GitHub se han encontrado con este problema a la hora de identificar los *tokens* de autentificación y descubrir que no podían diferenciar unos tipos de otros.
En [Behind GitHub's new authentication token formats](https://github.blog/2021-04-05-behind-githubs-new-authentication-token-formats/) nos lo cuentan.

El formato de algunos *tokens* antiguos están codificados en formato hexadecimal de 40 caracteres y esto los hace indistinguibles de otros que están codificados de la misma forma, pero que son de otros tipos.
Y esto es un problema.

> Many of our old authentication token formats are hex-encoded 40 character strings that are indistinguishable from other encoded data like SHA hashes.

Consideran, igual que otros, que la mejor forma de diferenciar estos elementos es mediante un prefijo, y por eso los están sustituyendo.

> As we see across the industry from companies like Slack and Stripe, token prefixes are a clear way to make tokens identifiable. We are including specific 3 letter prefixes to represent each token, starting with a company signifier, `gh`, and the first letter of the token type. 

Pero aún querían ir más allá, añadiendo sumas de comprobación (*checksums*).

> Identifiable prefixes are great, but let's go one step further. A checksum virtually eliminates false positives for secret scanning offline. We can check the token input matches the checksum and eliminate fake tokens without having to hit our database.

Y para hacerlo, han seleccionado el algoritmo C·C32

> We start the implementation with a CRC32 algorithm, a standard checksum algorithm. We then encode the result with a Base62 implementation, using leading zeros for padding as needed.  
