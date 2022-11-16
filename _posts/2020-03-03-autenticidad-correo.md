--- 
layout: post
title: "Algunos datos sobre la seguridad en los dominios más importantes"
date: "Tue Mar 03 15:05:01 +0100 2020"
category: seguridad
tags: [seguridad, correo, protocolos, estadísticas, demoscopía]
imagefeature: http://live.staticflickr.com/2120/2442636467_4f8c7a19d8.jpg
---

<a href="https://www.flickr.com/photos/fernand0/2442636467/" title="Rimas populares "><img src="http://live.staticflickr.com/2120/2442636467_4f8c7a19d8.jpg" alt="Rimas populares " width="240" style="float:left; margin:5px"></a>
En [Email authentication: SPF, DKIM and DMARC out in the wild](https://blog.jonlu.ca/posts/spf-dkim) un repaso de las distintas tecnologías de autentificación de correo y su uso por ahí.

Empieza recordando que el correo utiliza protocolos muy antiguos y que nacieron en épocas más 'apacibles' de la red.

> Email authentication has had a turbulent history - SMTP did not have a native form of authentication when it was designed, and all modern authentication methods are built on top of that system.

Hay una cantidad de métodos que permiten mejorar la cosa, como SPF, DKIM, y DMARC y el objetivo era verificar cuánto se utilizan.

>  Since then we’ve got a variety of tools to attempt to verify emails, including SPF, DKIM, and DMARC, and I wanted to explore the actual usage of these authentication methods by the most popular sites 

SPF (Marco de política de remitente, *Sender Policy Framework* permite al propietario de un dominio especificar los servidores desde los que envía correo y al receptor verificar los remitentes de un determinado dominio:

> SPF, or Sender Policy Framework, is a protocol that allows the owner of a domain to specify which mail servers they’ll be sending mail from. 

Sin embargo, de los 100 dominios más importantes casi todos lo usan con 'suavidad':

> For the top 100 domains, 50 of them have all set to softfail, whose intended action is accept but mark - this effectively says that any email received from a non-designated sender should be accepted but “marked” (which has no specific action associated - some providers drop the email, others send to junk, and others send to inbox).

Y algo parecido sucede con las 500 empresas más importantes según Fortune.

DKIM (Correo Identificado con Claves de Dominio, *DomainKeys Identified Mail*) utiliza claves que se publican en el DNS y que también pueden utilizarse para verificar que los correos vienen de donde deben.
Desafortunadamente no es fácil verificar su uso en un análisis como el que se realizó.

Finalmente, DMARC (Autentificación, Informe y Conformidad basada en el dominio de un mensaje *Domain-based Message Authentication, Reporting and Conformance*) es otro mecanismo que permite publicar una política en el DNS para especificar qué mecanismo se utiliza de los anteriores.

De los 100 dominios más importantes sólo 74 lo tienen activado:

> Of the top 100, only 74 of them have DMARC policies set up.

Y para las empresas del Fortune 500 la cosa baja un poco:

> Of the fortune 500, only 329 of them have DMARC policies set up, or a 66% implementation rate.

Otra herramienta sería el DNSSEC (DNS seguro) y en este caso, sólo un 6% de los 100 más importantes lo tienen y para el Fortune 500 estaríamos hablando de un 2.8%.

> For the Top 100 sites, only 6 of them are using DNSSEC (a 6% implementation rate). For the Fortune 500, it’s even worse, at 14, or a 2.8% implementation rate.

En definitiva, una tasa baja de adopción y en los casos que se adopta, sin demasiado interés.

> I was fairly surprised at the low adoption rates for the various security features above. If I had to guess it’s because of the haphazard nature of email systems growth. When there wasn’t one standardized security methodology from the beginning, each system will slowly build out its own, becoming a frankenstein monster of proprietary software and incorrectly implemented standards.


