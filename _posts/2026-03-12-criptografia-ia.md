---
layout: post
title: "Usando IAs para portar código"
date: "2026-03-12 14:00:00 +0000"
category: seguridad
tags:
- seguridad
- código
- IA
- rust
- Microsoft
imagefeature: "https://live.staticflickr.com/65535/55109725153_0f03f9db1c_z.jpg"
---

<a data-flickr-embed="true" href="https://www.flickr.com/photos/fernand0/55109725153/" title="Buque carguero Humbergracht"><img src="https://live.staticflickr.com/65535/55109725153_0f03f9db1c_z.jpg" width="640" height="427" alt="Buque carguero Humbergracht"/></a><script async src="//embedr.flickr.com/assets/client-code.js" charset="utf-8"></script>

En el mundo actual, con las IAs generativas trabajando a todo trapo y mejorando a buen paso, la pregunta no es si se hará alguna tarea concreta con ellas, sino  cuando.

En este caso, en  [Rewriting SymCrypt in Rust to modernize Microsoft’s cryptographic library](https://www.microsoft.com/en-us/research/blog/rewriting-symcrypt-in-rust-to-modernize-microsofts-cryptographic-library/) nos cuentan una experiencia de Microsoft re-escribiendo una biblioteca criptográfica con la ayuda de una de estas IAs.

Nos hablan del proceso de verificación formal para asegurarse de que lo que obtienen es correcto y algunas otras pruebas.

> Formal verification will confirm that implementations behave as intended and don’t deviate from algorithm specifications, critical for preventing attacks. We’ll also analyze compiled code to detect side-channel leaks caused by timing or hardware-level behavior.

Porque utilizar la IA y aceptar sus resultados sin más sería suicida, ¿no es así?

Interesante.

