--- 
layout: post
title: "Técnicas de Facebook para evitar el bloqueo de la publicidad"
date: "Mon Feb 24 15:05:01 +0100 2020"
category: desarrollo
tags: [desarrollo, web, publicidad, bloqueador, addblocker, trucos]
imagefeature: http://live.staticflickr.com/3490/3240520691_9fbe8bc55c.jpg
---

<a href="https://www.flickr.com/photos/fernand0/3240520691/" title="Anuncio de baja tecnología"><img src="http://live.staticflickr.com/3490/3240520691_9fbe8bc55c.jpg" alt="Anuncio de baja tecnología" width="240" style="float:left; margin:5px"></a>
En [How Facebook Avoids Ad Blockers](https://www.dylanpaulus.com/2019-11-24-how-fb-avoids-adblockers/) un poco de web y cómo la conocida empresa evita que bloqueemos sus anuncios.

Hoy en día es bastante habitual que naveguemos con algún sistema para evitar ver anuncios. En el caso de Facebook, se utilizan algunos trucos para que no tengamos otro remedio que verlos.

Por ejemplo, la etiqueta de anuncio está separada carácter a carácter:

> At first glance blocking these ads seems simple. Look for elements with the text containing 'Sponsored'. [...] First, Facebook doesn't actually have 'Sponsored' in their HTML. At least, not together as we would think. In the DOM, 'Sponsored' is actually broken up character by character.

No sólo eso, sino que la 'esconde' en los atributos de las etiquetas:

```
<span>
  <span data-content="S"></span>
  <span data-content="p"></span>
  <span data-content="o"></span>
 ...
```

Y también utiliza otras técnicas de ofuscación, insertando textos intermedios y otras 'diabluras', como caracteres invisibles:

> These values are entirely random characters, with a random number of DOM nodes between them. Invisible characters.

Curioso.
