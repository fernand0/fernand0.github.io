---
layout: post
title: Formas alternativas de conocer mejor a nuestros atacantes.
date: 2021-04-05 15:00:00 +0000
category: seguridad
tags:
- seguridad
- atacantes
- API 
- dropbox
imagefeature: 'http://live.staticflickr.com/3903/15367063802_080a374d2f.jpg'

---
<a href="https://www.flickr.com/photos/fernand0/15367063802/" title="Tanque "><img src="http://live.staticflickr.com/3903/15367063802_080a374d2f.jpg" alt="Tanque " width="240" style="float:left; margin:5px"></a>
Ante un incidente de segurida la respuesta tradicional es utilizar el registro de actividad (los *logs*) pero esta no es la única alternativa y en [Using API's to Track Attackers](https://isc.sans.edu/forums/diary/Using+APIs+to+Track+Attackers/26472/) nos dan algunas ideas sobre el tema.

Un atacante utiliza el API de Dropbox para conseguir algunos datos interesantes.

> The attackers reused exactly the same piece of coded (link above) to decrypt the master key - hey, why reinvent the wheel? To exfiltrate data, they decided to use Dropbox. The well-known file sharing service provides indeed a nice Python interface to its API[3] which is very easy to use...

De paso, nos hablan un poco de instrospección en Python:

> When you don't have experience with Python library objects, your first reflex must be to search for the available methods via dir()

Y, en este caso, sobre la obtención de información del atacante.

> The very first interesting method to use is `users_get_current_account()` to get information about the account. Now, we know more information about the attackers.

Nunca se sabe dónde podemos conseguir la mejor información.


