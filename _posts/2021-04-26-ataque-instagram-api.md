---
layout: post
title: Ataques a través de fallos en códigos de terceros
date: 2021-04-26 15:00:00 +0000
category: seguridad
tags:
- seguridad
- terceros
- ataques 
- instagram
imagefeature: 'http://live.staticflickr.com/8394/10208926684_df47fdd2c0.jpg'
---
<a href="https://www.flickr.com/photos/fernand0/10208926684/" title="2013-10-11-facebook "><img src="http://live.staticflickr.com/8394/10208926684_df47fdd2c0.jpg" alt="2013-10-11-facebook " width="240" style="float:left; margin:5px"></a>
Cuando deseamos atacar una aplicación, un tema al que no siempre se presta adecuada atención es a la 'cadena de suministro'; esto es, otras bibliotecas y aplicaciones que nuestra aplicación utiliza.

En [#InstaHack: how researchers were able to take over the Instagram App using a malicious image](https://blog.checkpoint.com/2020/09/24/instahack-how-researchers-were-able-to-take-over-the-instagram-app-using-a-malicious-image/) habla de Instagram, el conocido servicio para compartir imágenes y cómo encontraron una vulnerabilidad que permitía atacar una cuenta simplemente enviándole una imagen maliciosa.

Por un lado, tenemos una aplicación que 'necesita' un conjunto de permisos muy amplio en nuestro sistema.

> But what happens when we`re talking about an application that has extensive permissions on your device?  If the application is hacked, the hacker will have easy access to your GPS data, camera, microphone, contacts, and more.

Se trata, como casi todas, de una aplicación que utiliza ampliamente código de terceros.

>  Instead, they use 3rd party libraries to handle common (and often complicated) tasks such as image processing, sound processing, network connectivity, and so on. 

Y, en este caso, utilizaban código de un proyecto que tenía algún fallo y que permitía que cuando se le enviaba la imagen y esta se almacenaba en el dispositvo, se podía producir un ataque al abrir la aplicación.

> In the attack scenario we describe in our research, an attacker can simply send an image to their target victim via email, WhatsApp or another media exchange platform. The target user saves the image on their handset, and when they open the Instagram app, the exploitation takes place, allowing the attacker full access to any resource in the phone that is pre-allowed by Instagram.

Con esto era posible acceder a los datos o provocar una denegación de servicio, dejando inutilizada la aplicación.

Al informar a Facebook (el propietario de Instagram) sobre el tema descubrieron que el problema era un desbordamiento de enteros (los grandes olvidados en los ya de por sí olvidados desbordamientos) y lo arregló con rapidez.

> We have responsibly disclosed our findings to Facebook and the Instagram team. Facebook’s advisory was very responsive and helpful, they have described this vulnerability as an “Integer Overflow leading to Heap Buffer Overflow” and issued a patch to remediate the issue on the newer versions of the Instagram application on all platform.

Interesante.


