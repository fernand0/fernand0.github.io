--- 
layout: post
title: "Protegiendo la intimidad de los usuarios de Signal"
date: "Mon Jan 11 15:02:01 +0100 2021"
category: seguridad
tags: [seguridad, privacidad, intimidad, secreto, canales]
imagefeature: http://live.staticflickr.com/8523/8524350213_4887ed4ddf.jpg
---

<a href="https://www.flickr.com/photos/fernand0/8524350213/" title="Fwd: Libro. Intimidades "><img src="http://live.staticflickr.com/8523/8524350213_4887ed4ddf.jpg" alt="Fwd: Libro. Intimidades " width="240" style="float:left; margin:5px"></a>
En [ Expanding Signal GIF search](https://signal.org/blog/signal-and-giphy-update/) nos cuentan como han implantado la búsqueda de GIFs animados para su herramienta de comunicación y lo hacen cuidado nuestra privacidad. Esencialmente, cuando se busca información en un proveedor ([Giphy](https://giphy.com/)) en este caso, primero se habla de cómo se evita que Signal 'vea' el contenido que consultamos para obtener una imagen (gracias al protocolo TLS y a que no se colocan como intermediarios). A la vez, Signal aparece como solicitante para Giphy, así que el servicio no puede saber quién hizo la petición:

> Since communication is done via TLS all the way to GIPHY, the Signal service never sees the plaintext contents of what is transmitted or received. Since the TCP connection is proxied through the Signal service, GIPHY doesn’t know who issued the request.

Sin embargo, querían ir un poco más allá, lanzando varias peticiones y francionando el contenido en paquetes para que sea más difícil de conocerlo.

> Instead of making a normal request, it picks a block size (in this case 6 bytes), and issues sequential range requests for that amount. For the third and final request, there is only 1 byte remaining to be retrieved, but it instead makes an overlapping request for the final 6 bytes, and discards the first 5 bytes of the final request.

Intersante y curioso.
