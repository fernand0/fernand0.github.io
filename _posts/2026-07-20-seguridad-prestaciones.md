---
layout: post
title: "¿Seguridad o prestaciones? Compromisos"
date: "2026-07-20 14:00:00 +0000"
category: seguridad
tags:
- seguridad
- deepfakes
- IA
imagefeature: "https://live.staticflickr.com/65535/55219859374_ec33e74ec6_z.jpg"
---

<a data-flickr-embed="true" href="https://www.flickr.com/photos/fernand0/55190920280/in/dateposted/" title="Reloj grifo de jade"><img src="https://live.staticflickr.com/65535/55190920280_b09de2a8da_z.jpg" width="427" height="640" alt="Reloj grifo de jade"/></a><script async src="//embedr.flickr.com/assets/client-code.js" charset="utf-8"></script>

No estoy muys seguro sobre en qué habrá terminado esto pero me parece interesante por varios motivos: [Ubuntu disables Intel GPU security mitigations, promises 20% performance boost](https://arstechnica.com/security/2025/06/ubuntu-disables-intel-gpu-security-mitigations-promises-20-performance-boost/).

Por un lado, está claro que añadir controles de seguridad hace que el código sea más lento (en este caso parece que mucho), y más complejo (se añaden instrucciones para vigilar que no pasen cosas y estar seguros de que sucden las adecuadas).

En este caso, además, los controles de seguridad vienen de un fallo de diseño por la ejecución predictiva (Recordar <a href="https://arstechnica.com/gadgets/2018/01/meltdown-and-spectre-every-modern-processor-has-unfixable-security-flaws/">“Meltdown” and “Spectre:” Every modern processor has unfixable security flaws</a>).

Según Ubuntu, este sería un problema suficientemente bien manejado en el kernel y, por lo tanto, los controles que añadían serían innecesarios.

> At this point, Spectre has been mitigated in the kernel, and a clear warning from the Compute Runtime build serves as a notification for those running modified kernels without those patches. For these reasons, we feel that Spectre mitigations in Compute Runtime no longer offer enough security impact to justify the current performance tradeoff.

La ganancia no es pequeña, como dice el titular un 20% de mejora.

Más aún, parece que estos fallos no están siendo atacados porque el esfuerzo no compensa (aunque ya sabemos que todo depende del sistema y el nivel de la información que protege).

> “Nobody bothers attacking these vulns because it takes a lot of engineering time to implement attacks against them to any useful level of rigor, and getting any interesting data back outside very targeted scenarios is very unlikely (plus it’s noisy due to the number of iterations you need to do on these types of side-channels),” independent researcher Graham Sutherland wrote on Mastodon. “The economics just don’t stack up for attackers, especially when there are so many lower-effort higher-reward attack approaches they can throw at stuff.”

Interesante.
