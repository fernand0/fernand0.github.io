--- 
layout: post
title: "JMAP: evoluciones alternativas abiertas para el viejo correo electrónico"
date: "Tue Mar 26 15:05:01 +0100 2019"
category: seguridad
tags: [correo, internet, protocolos, IMAP, JMAP]
imagefeature: https://farm3.staticflickr.com/2120/2442636467_4f8c7a19d8_m.jpg
---



<a href="https://www.flickr.com/photos/fernand0/2442636467" title="Buzón"><img src="https://farm3.staticflickr.com/2120/2442636467_4f8c7a19d8_m.jpg" width="240"  alt="Buzón" style="float:left; margin:5px"></a>
Damos por supuesto el funcionamiento del correo como algo que hemos tenido siempre pero, igual exagero, yo estoy algo preocupado: no hay grandes avances ni evoluciones y todos damos por hecho el uso de los grandes proveedores. No tengo nada que objetar, pero sí que me preocupa que esos grandes proveedores vayan cambiando los protocolos y el correo electrónico deje de ser lo que era. 
Por ejemplo, uno puede consultar su cuenta de GMail mediante IMAP o POP3 pero... cuando lo habilita, si no recuerdo mal nos avisan de que es un protocolo 'menos seguro'. 
Quien dice eso, si echamos un vistazo a los clientes el panorama tampoco es muy halagüeño: los clientes parece que van evolucionando poco y casi por inercia, rendidos ante la 'potencia' de los clientes web. Y no hay una gran diversidad, ni siquiera en el mundo móvil donde lo que podemos encontrar son cambios estéticos sobre algunas bases comunes. Para mi sería paradigmático el caso de Ubuntu Touch que, abandonado como está y en manos de voluntariosos desarrolladores nunca ha tenido un buen cliente de correo (aunque el que promovía traía ideas interesantes) lo que significaría que Ubuntu no consideró esa pieza como algo importante en sus desarrollos (y nadie lo ha hecho después).

Seguro que solo son impresiones y el tiempo nos lo dirá pero me gustó leer [JMAP: It’s like IMAP But Not Really](https://unencumberedbyfacts.com/2019/01/24/jmap-its-like-imap-but-not-really/) del que ya había leído algo pero no había entendido muy bien en qué consistía. En esta nota nos explican que JMAP sería un sustituto de IMAP/SMTP (protocolos de lectura y envío de mensajes de correo) basado en JSON, *JMAP (JSON Meta Application Protocol)* y que parece que trata de atacar a la complicación que supone actualmente desarrollar un cliente de correo (y que, de paso, daría la razón a Google explorando sus propios mecanismos y APIs).

Nos dicen también que se trata de una API REST que mejora sustancialmente al protocolo IMAP:

> Astute readers may have added this up by now, but just to clarify: JMAP is a modern REST like API that can do everything IMAP does but better.

Además de ser abierto, moderno...

¿Hay esperanza en el mundo del correo electrónico?
