--- 
layout: post
title: "Algunas intrucciones útiles cuando estamos usando una terminal"
date: "Fri Feb 22 15:05:01 +0100 2019"
category: desarrollo
tags: [desarrollo, terminal, instrucciones, shell, alias]
imagefeature: https://c1.staticflickr.com/5/4010/5160299221_e74e74a038_m.jpg
---


<a href="https://www.flickr.com/photos/fernand0/5160299221" title="Terminal"><img src="https://c1.staticflickr.com/5/4010/5160299221_e74e74a038_m.jpg" width="240"  alt="Terminal" style="float:left; margin:5px"></a>
Me reconozco un gran usuario de la línea de instrucciones en una terminal: cuando se maneja medianamente la productividad puede ser excelente. Por eso me gustó leer [Some of My Favorite Shell Aliases From Over the Years](https://danielmiessler.com/blog/some-of-my-favorite-shell-aliases-from-over-the-years/) donde Daniel Miessler nos da algunas recomendaciones.
Los expresa en forma de alias, para tener que teclear menos.

Por ejemplo, para buscar:

`$ alias f="find . -name"`

O algo que pregunta muchas veces la gente nueva, ¿cómo se mi IP?:

`$ alias gip="curl ipinfo.io/ip && curl ipinfo.io/org"`

Un generador de contraseñas:

`$ alias np="openssl rand -base64 24"`

Y algunos más. Interesante.
