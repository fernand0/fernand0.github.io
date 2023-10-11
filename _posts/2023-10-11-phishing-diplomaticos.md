---
layout: post
title: "Phishing y diplomáticos: cambiando los objetivos"
date: "2023-10-11 15:00:00 +0000"
category: seguridad
tags:
- seguridad
- phishing
- embajadas
- diplomacia
imagefeature: 'https://live.staticflickr.com/2921/14451469928_6bff96b6d4.jpg'
---
<a href="https://www.flickr.com/photos/fernand0/14451469928/" title="Diana cazadora "><img src="https://live.staticflickr.com/2921/14451469928_6bff96b6d4.jpg" alt="Diana cazadora " class="img-responsive img-centered"></a>

Se habla mucho del phishing porque todos tenemos hoy algún ejemplo que mostrar en nuestro teléfono móvil, o en nuestro correo, o en cualquiera de los sistemas de mensajería que utilizamos.
No se habla tanto (o se deja un poco más difuso) del tema de los ataques dirigidos a personas o colectivos concretos.

En [Diplomats Beware: Cloaked Ursa Phishing With a Twist](https://unit42.paloaltonetworks.com/cloaked-ursa-phishing/) nos hablaban de un servicio ruso especializado en diplomáticos.

Los ataques típicamente se desarrollan utilizando diferentes mecanismos que son habituales en el mundillo (no los traduzco):

> 
    * Notes verbale (semiformal government-to-government diplomatic communications)
>   * Embassies’ operating status updates
>   * Schedules for diplomats
>   * Invitations to embassy events

Este tipo de comunicaciones se envían habitualmente a la persona que se encarga de esos asuntos en la embajada.

> These types of lures are generally sent to individuals who handle this type of embassy correspondence as part of their daily jobs. They are meant to entice targets to open the files on behalf of the organization they work for.

Pero parece que la tendencia está cambiando y ahora estarían tratando de llegar directamente a los diplomáticos, en lugar de a sus países (a los que representan).

> Recently, Unit 42 researchers observed instances of Cloaked Ursa using lures focusing on the diplomats themselves more than the countries they represent.

Esto significa que tratarían de engañar a estas personas para que abran los mensajes (y se infecten) basando la comunicación en sus propios intereses y no como parte de su tarea profesional.

> These unconventional lures are designed to entice the recipient to open an attachment based on their own needs and wants instead of as part of their routine duties.

Además, este tipo de mensajes serían más susceptibles de poder ser reenviados, para alcanzar a un mayor número de objetivos, dentro y fuera de la organización.

> The lures themselves are broadly applicable across the diplomatic community and thus are able to be sent and forwarded to a greater number of targets. They’re also more likely to be forwarded to others inside of an organization as well as within the diplomatic community.

Los tiempos van cambiando.
