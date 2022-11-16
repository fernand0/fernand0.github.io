---
layout: post
title: "Obsolescencia de algoritmos criptográficos vs realidad"
date: "Thu Dec 15 16:25:01 +0100 2016"
category: seguridad
tags: seguridad criptografía hash sha1 sha2 navegadores demoscopía
imagefeature: https://scontent-fra3-1.cdninstagram.com/t51.2885-15/e35/13736867_876647612440788_744421225_n.jpg
---




<a href="https://www.instagram.com/p/BH742_VBtWA/" title="Enigma"><img src="https://scontent-fra3-1.cdninstagram.com/t51.2885-15/e35/13736867_876647612440788_744421225_n.jpg" alt=" Algunos trucos para esconder programas maliciosos "></a>
En [SHA-1 Deprecation: No Browser Left Behind](https://blog.cloudflare.com/sha-1-deprecation-no-browser-left-behind/) nos hablan sobre la obsolescencia del algoritmo de hash criptográfico [SHA1](https://en.wikipedia.org/wiki/SHA-1) con algunos datos como lo que costaría hoy en día generar colisiones (recordemos que en un algoritmo de hash el poder genera un mensaje diferente que tenga el mismo 'resumen', esto es, encontrar colisiones es uno de los principales problemas de seguridad):

> Computers keep getting faster and now SHA-1 is increasingly vulnerable to potential collision attacks. The estimate today is that it would likely cost around USD$700,000 to generate a SHA-1 collision. By 2021, the price is forecast to fall to just USD$43,000. 

También hacen algunos cálculos de cuánto se utiliza su sucesor, [SHA2]/(https://en.wikipedia.org/wiki/SHA-2):

>  To understand the impact, we spent the last few weeks testing browser connections to CloudFlare's network for SHA-2 support. We see approximately 1 trillion page views for more than 2.2 billion unique visitors every month, which gives us a pretty representative sample of global traffic.

Y la conclusión es que podrían utilizar este algoritmo un 98.1% de los navegadores observados por ellos que puede parecer mucho pero, en sus cuentas, deja fuera a un nada despreciable número de más de 37 millones de personas. En Estados Unidos la cosa sería un poco mejor:

> The United States has 99.26% SHA-2 support, making it the 15th most modern browser market (out of more than 190 countries we saw traffic from during our test). In fact, SHA-2 support in Western Europe and North America is universally over 99%.

pero, desde luego, no el mejor de los sitios con acceso a esta tecnología (15 puesto en el ranking de navegadores más modernos).

Lamentablemente, en la cola de esta lista están algunos de los países que probablemente necesitarían tener mejores sistemas de seguridad.

> Unfortunately, this list largely overlaps with lists of the poorest, most repressive, and most war torn countries in the world. In other words, after December 31st most of the encrypted web will be cut off from the most vulnerable populations of Internet users who need encryption the most. 

Y, claro, esto tiene como consecuencia que sitios como Alibaba o Facebook que quieren tener clientes en esas zonas menos protegidas admitan utilizar los algorimtmos menos seguros (lo que puede afectar a todo el mundo).

> For instance, Alibaba, the Chinese Internet commerce giant, supports SHA-1 fallback across many of its sites. That's not surprising given more than 6% of their Chinese customers could not securely buy from their online store if they only supported SHA-2.

> Facebook also supports SHA-1 fallback across many of their sites. 

Interesante.
