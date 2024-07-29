---
layout: post
title: "Algunas ideas sobre problemas de seguridad habituales en WordPress "
date: "2024-07-29 15:00:00 +0000"
category: seguridad
tags:
- web
- WordPress
imagefeature: "https://live.staticflickr.com/65535/51334548326_e297d749c8_z.jpg"
---

<a data-flickr-embed="true" href="https://www.flickr.com/photos/fernand0/51334548326/in/photolist-2gyJfDL-2hfQ4cw-2hxQfGx-2idYLKA-2jaqkz3-2kx71fT-2kFMYS4-2kMYwwu-2kMYX5U-2kUTtTy-2kWjdDB-2mdfYKq-2mdfYLN-2nffsJm-2prRLHM-2pEwCSo-2pEwCU2-2pK3CZt-2pMN8kU-2f3D3T4-s2ioZC-s2rqsc-BFN6y9-CA8oFN-Ev3AE3-EYwm9m-FgzRAP-FqF26E-G3FS1y-G5ZudM-PRRmtw-24h9dgM-PUBziP-QbmpPJ-Qe9Vc6-QEpmoz-RpkB9A-RsTxQi-RBPJCT-RRmD2H-RVQmnq-SEtYKH-T2HibJ-T6mt6a-e5L8WT-3Ev3fi-589mHS-97n6Mg-zmZ2-d9XeHs" title="Detalle de la puerta"><img src="https://live.staticflickr.com/65535/51334548326_e297d749c8_z.jpg" width="427" height="640" alt="Detalle de la puerta"/></a><script async src="//embedr.flickr.com/assets/client-code.js" charset="utf-8"></script>

Soy un usuario bastante básico de WordPress: algún sitio de los que ofrecen gratis y alguno más de los que nos proporcionan en el trabajo para diversos asuntos. Pero los fallos de seguridad siempre son interesantes, porque casi siempre se pueden extraer conclusiones y enseñanzas para nuestro contexto. Incluso cuando no sea el mismo.

Por eso hoy traemos [The Real Attack Vector Responsible for 60% of Hacked WordPress Sites in 2023](https://wewatchyourwebsite.com/the-real-attack-vector-responsible-for-60-of-hacked-wordpress-sites-in-2023/) donde se habla de los *plugins* desactualizados como punto principal de los ataques a sitios de WordPress.

>  A particularly pervasive one is the unsubstantiated claim that “95% of WordPress hacks are due to outdated plugins or themes.“


Esencialmente, alguien contrata la realización de su web, se la hacen con esta tecnología y luego vienen los problemas: o no se contrata el mantenimiento, o éste es deficienten....

Luego entra en detalles sobre el tipo de problemas que suelen ocurrir:

* Fallos en la autentificación

> Authentication Compromise (stolen session cookies + compromised credentials) and

Los robos de *cookies*  tienen que ver algunas veces con el acceso local con algún tipo de sistema de robo.

Los robos de usuarios y contraseñas se pueden producir de formas similares, y también son frecuentes.

* Fallos en los *plugins*, los 'temas' y las funcionalidades básicas.

> Plugin, Theme & Core vulnerabilities

En este caso, cuando aparecen vulnerabilildades está bastante claro que después aparecerán los ataques.

> Meaning, we can clearly tie the presence of a vulnerability to a potential exploit of the vulnerability.

Los consejos: desconectarse del sitio cuando terminsmos, *logout*, para evitar el robo de sesiones, utilizar doble factor de autentificación, actualizarlo todo cuando toca...
