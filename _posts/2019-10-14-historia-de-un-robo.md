--- 
layout: post
title: "Alguien cambió lo que no debía. Un caso real"
date: "Mon Oct 14 16:05:01 +0100 2019"
category: seguridad
tags: [seguridad, ruby, gems, gemas, passwords, contraseñas, claves, 2fa]
imagefeature: https://live.staticflickr.com/8317/7894543082_2074cfdf1d_m.jpg
---

<a href="https://www.flickr.com/photos/fernand0/7894543082" title="Vidrios de colores"><img src="https://live.staticflickr.com/8317/7894543082_2074cfdf1d_m.jpg" width="240"  alt="Vidrios de colores" style="float:left; margin:5px"></a>
En [strong_password v0.0.7 rubygem hijacked](https://withatwist.dev/strong-password-rubygem-hijacked.html) Tute Costa nos cuenta cómo descubrió que alguien había robado una cuenta y había cambiado una de las gemas (*gems*) que utiliza su aplicación.

Aparentemente, le habían robado las credenciales al autor a través de uno de esos robos habituales en diversos servicios y la mala práctica de reutilizar las contraseñas entre distintos servicios. Sin doble factor de autentificación.

Además, el mensaje podría ser que estas cosas pasan hasta en las mejores familias. O algo así.
