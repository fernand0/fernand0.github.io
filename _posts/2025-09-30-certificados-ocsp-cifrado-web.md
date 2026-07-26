---
layout: post
title: "Revocación de certificados, el fin de OCSP"
date: "2025-09-30 15:00:00 +0000"
category: seguridad
tags:
- seguridad
- certificados
- OCSP
imagefeature: "https://live.staticflickr.com/8397/8667994367_004036e159_z.jpg"
---
<a data-flickr-embed="true" href="https://www.flickr.com/photos/fernand0/8667994367/" title="Teatro romano de Mérida. Columnas"><img src="https://live.staticflickr.com/8397/8667994367_004036e159_z.jpg" width="640" height="427" alt="Teatro romano de Mérida. Columnas"/></a><script async src="//embedr.flickr.com/assets/client-code.js" charset="utf-8"></script>

Me gusta hacer el ejercicio con personas más o menos técnicas de preguntar quén ha examinado alguna vez un certificado de una página web (el famoso candadito); suele resultar que casi nadie lo ha mirado y entonces aprovecho para mirar la información que aparece y lo confusa que es. Incluso, como digo, para personas de perfil más o menos técnico.
Lo malo es que entre los consejos de seguridad habituales suele estar el de examinarlos. Y lo peor es que quién más quién menos se ha encontrado con una página legítima (¿en la red interna de su empresa? ¿en alguna organización poco cuidadosa con esos temas?) en la que ha necesitado darle al botón de 'me fío, sigue adelante' para poder llevar a cabo su cometido.

No tiene mucho que ver (o sí) pero lo cierto es que los certificados son unos grandes maltratados.

Los certificados suelen tener la posibilidad de ser revocados (esto es, decir que ya no valen) pero, adivinen: todavía menos gente mira esa información. Hace unos meses la gente de Let's Encrypt anunciaba el [Ending OCSP Support in 2025](https://letsencrypt.org/2024/12/05/ending-ocsp) que supondría el fin del uso del protocolo OCSP (*Online Certificate Status Protocol*).
en [The Slow Death of OCSP ](https://www.feistyduck.com/newsletter/issue_121_the_slow_death_of_ocsp) comentaban con cierto detalle el tema y por eso lo traemos aquí.

Este protocolo pretende proporcionar apoyo a la revocación en tiempo real de los certificados y su verificación.

> As the name suggests, OCSP is intended to support real-time certificate revocation checking.

El problema es que no se ha utilizado mucho al principio, y cuando se empezó a usar más había problemas de rendimiento.

> Because browsers were not implementing OCSP, CAs got used to receiving no traffic to their OCSP servers and didn’t spend a lot of time supporting that infrastructure. By the time the usage eventually grew, OCSP performance problems were common and frequent.

Había más problemas, que el autor detalla.

La alternativa son las listas de revocación de certificados, CLR (*Certificate Revocation Lists*), que permitirían a los emisores de estos elementos publicar su lista, que se pueden descargar de forma periodica y usarse para la verificación.

> From the very beginning, we had Certificate Revocation Lists, or CRLs. The idea behind these lists was simple: every certificate issuer would also track and continuously publish a complete list of all revoked certificates. Certificate consumers would periodically download the CRLs from the CAs they cared about and verify that the certificates they were using were still valid.

Esto ha cambiado un poco porque ahora son los responsables (y otros agentes) de los navegadores los que gestionan estas listas.

> Instead of user agents consuming the CRLs directly, major browser vendors (and, presumably, operating systems) maintain their proprietary revocation checking built on continuous processing of all known CRLs.

Termina diciendo que probablemente la mejor solución es que los certificados tengan vidas relativamente cortas (unos días), y así no hay que preocuparse de revocarlos.

> At the end of the day, with short-lived certificates, we—finally—have a plausible revocation checking story, even if it doesn’t actually involve any revocation.

Curioso como los pilares de nuestra seguridad tienen a veces tantas dificultades para alcanzar situaciones razonables.
