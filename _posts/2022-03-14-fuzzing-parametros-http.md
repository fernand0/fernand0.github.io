---
layout: post
title: "HTTP, fuzzing e inseguridad con componentes seguras"
date: "2022-03-14 15:00:00 +0000"
category: seguridad
tags:
- seguridad
- fuzzing
- HTTP
- interacciones
imagefeature: 'https://live.staticflickr.com/65535/49420833183_739746d311.jpg'
---
<a href="https://flickr.com/photos/fernand0/49420833183/" title="Banderas y frontera "><img src="https://live.staticflickr.com/65535/49420833183_739746d311.jpg" alt="Banderas y frontera " width="240" style="float:left; margin:5px"></a>
Ya hemos hablado a veces de las herramientas de *fuzzing* y cómo podían permitir encontrar fallos de seguridad. También hemos hablado de los parámetros del protocolo HTTP y algunas manipulaciones.
En esta ocassión podemos hablar de la reunión de ambos mundos. En [New differential fuzzing tool reveals novel HTTP request smuggling techniques](https://portswigger.net/daily-swig/new-differential-fuzzing-tool-reveals-novel-http-request-smuggling-techniques) nos contaban cómo unos investigadores habían descubierto nuevos fallos utilizando herramientas de *fuzzing*.

> In a white paper the researchers discuss how they discovered a wealth of new vulnerabilities using the fuzzing tool, which they said can be used by bug bounty hunters and researchers alike.

Nos recuerda el fallo de manipulación de peticiones HTTP del que se empezó a hablar en 2005.

> HTTP request smuggling, which first emerged in 2005, interferes with how websites process sequences of HTTP requests received from users.

Los fallos a los que se refieren aparecen cuando hay balanceadores de carga y reenvíos de cabeceras, que pueden ser utilizados para hacer pasar algunas peticiones a través de esa infraestructura.

> If there is a discrepancy between the front- and back-end servers, it can allow attackers to smuggle hidden requests through the proxy.

Es un ejemplo de lo que se llama interacción insegura entre componentes seguras: cada una de ellas puede ser perfectamente válida, pero las diferencias entre ellas pueden provocar problemas.

> The paper reads: "These processors may not necessarily be individually buggy; but when used together, they disagree on the parsing or semantics of a given HTTP request, which leads to a vulnerability.

Las técnicas se basan en enviar ligeras variaciones entre peticiones HTTP para detectar inconsistencias y posibles problemas.

>  It exercises two target servers with the same mutated request, and compares the responses to identify discrepancies that lead to smuggling attacks.  

En definitiva, tener componentes seguras no garantiza la seguridad de un sistema, porque la seguridad tiene que ser una propiedad del sistema completo.

> "Secure components do not necessarily make a secure system; security is an
emergent property of the system as a whole.

Muy interesante.
