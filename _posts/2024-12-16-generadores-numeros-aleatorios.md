---
layout: post
title: "Los generadores de números seudoaleatorios y la seguridad"
date: "2024-12-16 15:00:00 +0000"
category: seguridad
tags:
- seguridad
- RNG
- PRNG
- CSPRNG
- seudoaleatorios
imagefeature: "https://live.staticflickr.com/1255/1301539362_daa1107f13_z.jpg"
---
<a data-flickr-embed="true" href="https://www.flickr.com/photos/fernand0/1301539362/in/photolist-2Z1JiQ-5mvoPy-qRSfg" title="Los dados del r5"><img src="https://live.staticflickr.com/1255/1301539362_daa1107f13_z.jpg" width="480" height="640" alt="Los dados del r5"/></a><script async src="//embedr.flickr.com/assets/client-code.js" charset="utf-8"></script>

Esta es la edición de final de año del recordatorio de que los números aleatorios y las computadoras no se llevan bien. En esta ocasión de la mano de John D. Cook, y [RNG, PRNG, CSPRNG](https://www.johndcook.com/blog/2024/10/16/rng-prng-csprng/).

Empieza recordándonos que la mayoría de generadores de números aleatorios son generadores de números **seudo**aleatorios (*pseudorandom number generators PRNGs)*.

> Most random number generators are pseudorandom number generators (PRNGs). The distinction may be pedantic or crucial, depending on context. In the context of cryptography, it’s critical.

Y la vuelta de tuerca es que para la criptografía (y seguridad en general) no nos basta con estos números (que sería suficientes para simulaciones, integración numérica, juegos, ...) sino que necesitamos los llamados generadores **criptogr´ficos seguros** de números seudoaleatorios *(cryptographically secure pseudorandom number generator, CSPRNG)*.

> A PRNG may be suitable for many uses—Monte Carlo simulation, numerical integration, game development, etc.—but not be suitable for cryptography. A PNRG which is suitable for cryptography is called a CSPRNG (cryptographically secure pseudorandom number generator).

¿La razón? Hay técnicas de análisis criptográfico muy pontentes, que pueden ayudar si hay sesgos o la calidad de los números generados no es buena por algún motivo.

>  If a PRNG fails statistical tests, it has some sort of regularity that potentially could be exploited by cryptanalysis.

Los generadores de números seudoaleatorios tienen buenas propiedades desde el punto de vista de la estadística, pero no tienen por qué ser seguros.

> A PRNG may have excellent statistical properties, and pass standard test suites for random number generators, and yet be insecure.

Un generador de números aleatorios físico, con buenas propiedades estadísticas podría tener, sin embargo, buenas propiedades desde el punto de vista de la seguridad. Nombra el conocido caso de las lámparas de lava de Cloudflare ([How do lava lamps help with Internet encryption?](https://www.cloudflare.com/en-gb/learning/ssl/lava-lamp-encryption/))

> I suspect that a physical RNG with good statistical properties will have good cryptographic properties as well, contrary to the usual case. Cloudflare famously uses lava lamps to generate random bits for TLS keys.

Pero también puede ocurrir que los sistemas generadores físicos fallen las pruebas estadísticas (por ejemplo, que aparezcan sesgos).

> A physical RNG might fail statistical tests. For example, maybe the physical process is truly random but biased.

¿Alguien de estadística en la sala?
