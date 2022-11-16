--- 
layout: post
title: "Reducción de costes para un servicio en la nube"
date: "Tue Mar 19 15:05:01 +0100 2020"
category: nube
tags: [nube, cloud, costes, reducción, web, aws]
imagefeature: https://live.staticflickr.com/8447/27802095304_02cd235c0e.jpg
---

<a href="https://www.flickr.com/photos/fernand0/27802095304/" title="Dinero "><img src="https://live.staticflickr.com/8447/27802095304_02cd235c0e.jpg" alt="Dinero " width="240" style="float:left; margin:5px"></a>
La promesa de la nube (ajena) es ahorro en costes (no tener que adquirir, instalar, ni mantener infraestructura). No obstante, eso no significa que no haya costes que haya que vigilar y tratar de mejorar. De eso nos habla [Three ways to reduce the costs of your HTTP(S) API on AWS](https://gameanalytics.com/blog/reduce-costs-https-api-aws.html).

Empiezan hablando de sus medidas: reciben, almacenan y procesan eventos relacionados con juegos de 1200 millones de jugadores en cerca de 90,000 juegos.

> Here at GameAnalytics, we receive, store and process game events from 1.2 billion monthly players in nearly 90,000 games.

Esto se traduce en alrededor de cinco mil millones de peticiones diarias, cada una de ellas con dos o tres eventos de unos pocos kilobytes.

> We get approximately five billion requests per day, each typically containing two or three events for a total of a few kilobytes.

Y eso tiene un coste, claro:

> So what would you guess is the greatest cost associated with running this system on AWS, with a fleet of EC2 instances behind a load balancer?

La mayoría, datos que van hacia afuera:

> We wouldn’t have guessed that the greatest part of the cost is for data transfer out. Data transfer in from the Internet is free, while data transfer to the Internet is charged between 5 and 9 cents per gigabyte.

Los trucos son sencillos, en algunos casos:

* Reducir las cabeceras HTTP,  para bajar de 333 bytes a 109

> Sending 109 bytes instead of 333 means saving $56 per day, or a bit over $1,500 per month.

* Reducir la negociación del TLS, basado en la recuperación de sesiones TLS.

> That leaves reducing the number of handshakes required by reducing the number of connections that the clients need to establish. [...] This reduced data transfer costs by an additional 8%.

* Verificar los certificados, que típicamente también son demasiado grandes. Sobre todo si hay una cadena de confianza para establecer la validez del nuestro.

> So given that the clients establish approximately two billion connections per day, we’d expect to save four terabytes of outgoing data every day. The actual savings were closer to three terabytes, but this still reduced data transfer costs for a typical day by almost $200.

Una lectura interesante.

