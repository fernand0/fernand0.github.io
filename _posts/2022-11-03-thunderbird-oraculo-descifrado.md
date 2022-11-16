---
layout: post
title: "Más fallos sofisticados: Thunderbird y la lectura de mensajes cifrados"
date: "2022-11-03 15:00:00 +0000"
category: seguridad
tags:
- seguridad
- ataques
- thunderbird
- cifrado
- javascript
- fuzzing
imagefeature: 'https://live.staticflickr.com/65535/52164028347_cc33b620a2.jpg'
---
<a href="https://www.flickr.com/photos/fernand0/52164028347/in/dateposted/" title="Bolas chinas concéntricas "><img src="https://live.staticflickr.com/65535/52164028347_cc33b620a2.jpg" alt="Bolas chinas concéntricas " class="img-responsive img-centered"></a>
En [Exploit Disclosure: Turning Thunderbird into a Decryption Oracle](https://pseudorandom.resistant.tech/disclosing-security-and-privacy-issues-in-thunderbird.html) nos cuentan varios fallos de seguridad y privacidad en alguna versión reciente del cliente de correo Thunderbird.

La peor de ellas, según el autor, sería la que permite engañar al programa para que descifre un mensaje y lo envíe de vuelta al atacante.

> At worst these vulnerabilities can by exploited by an adversary with access to a collection of intercepted encrypted messages to trick Thunderbird into decrypting any given message and sending the resulting plaintext back to the adversary. 

La detección se hizo utilizando *fuzzing*.
La cuestión es que, como en otros fallos que hemos comentado recientemente, el ataque es sofisticado y necesita unos cuantos pasos. Implica tener un mensaje de correo en texto formateado con html (que el programa no interetará en su configuración por defecto), pero que contenga una etiqueta *meta* (meta tag) con una directiva *refresh*.  El refresco tenía dos consecuencias, por lo visto: se accedía a la URL (fallo de privacidad), y algunas protecciones de Thunderbird se podían evitar.

> However, through fuzzing, we were able to find that when opening a text/html email containing a meta tag with a refresh directive, in the compose window, we were able to trigger a refresh of the rendering context.

Si se incluía una etiqueta de objeto (*tag object*) que hiciera referencia a una URL inválidad se podía conseguir ejecutar Javascript en un gestor (*handle*) de sucesos *onerror*.

> By also including an object tag referencing an invalid url we were able to execute javascript in the onerror handler.

A partir de aquí nos cuenta cómo pudo utilizar estos fallos para descifrar y enviar el mensaje, pero dejamos la lectura para las personas interesadas.

Lo que pueda fallar, fallará. Y alguien lo descubirá.
