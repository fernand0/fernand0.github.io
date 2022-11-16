---
layout: post
title: "Un estudio sobre correo autentificado en EEUU"
date: "Wed Jan 10 16:20:01 +0100 2018"
category: seguridad
tags: [seguridad, correo, autentificación, dmarc, empresas, eeuu, usa]
imagefeature: https://c2.staticflickr.com/2/1479/25614243111_e6fcefc935_m.jpg
---


<a href="https://www.flickr.com/photos/fernand0/25614243111" title="Correos"><img src="https://c2.staticflickr.com/2/1479/25614243111_e6fcefc935_m.jpg" width="240"  alt="Correos" style="float:left; margin:5px"></a>
El correo no deseado es una plaga. Pero a este se añade el correo que trata de hacerse pasar por alguien. No es una amenaza demasiado abundante (al menos para gente normal) pero el segundo afecta **mucho** al segundo: si no hay una cierta autentificación, cualquiera termina pasando nuestros filtros anti-spam y haciéndonos perder el tiempo.

En [Most email authentication implementations fail](https://www.helpnetsecurity.com/2016/12/05/email-authentication-implementations-fail/) hablaban de diversos estudios sobre [DMARC](https://dmarc.org/),

> DMARC, which stands for “Domain-based Message Authentication, Reporting & Conformance”, is an email authentication, policy, and reporting protocol. 

El resultado es (como suele pasar) bastante lamentable: aproximadamente tres cuartas partes de las empresas grandes que intentan utilizar el estándar no son capaces de utilizarlo con éxito para bloquear mensajes no autorizados.

> “Our investigation showed that using email authentication to monitor and control unauthorized email is extremely difficult for the majority of global companies,” said ValiMail CEO Alexander García-Tobar. “You might expect larger businesses with more resources to do a better job of governing the email going out under their names, but we found that most of them still miss the mark.”

Y así seguimos.
