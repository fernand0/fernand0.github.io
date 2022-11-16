---
layout: post
title: "Una introducción a la criptografía elíptica"
date: "Thu Jan 18 23:05:01 +0100 2015"
category: seguridad
tags: seguridad criptografía elíptica
---


<a href="https://www.flickr.com/photos/fernand0/14398983648/" title="Amon"><img src="https://farm3.staticflickr.com/2906/14398983648_5e6523628b_m.jpg" width="240"  alt="El escondido" style="float:left; margin:5px"></a>

La criptografía es de mis temas 'menos' favoritos en seguridad. Siempre nos avisan de que es algo difícil de hacer bien. Por lo tanto nos relega al papel de meros consumidores, eso sí, tratando de estar al día en los tamaños de claves, algoritmos criptográficos y esas cuestiones.

En [A (relatively easy to understand) primer on elliptic curve cryptography](http://arstechnica.com/security/2013/10/a-relatively-easy-to-understand-primer-on-elliptic-curve-cryptography/) se publicaba hace algunos meses justamente lo que dice el título: una introducción a la criptografía de curvas elípticas que puede servirnos como introducción para recordar/ponernos al día en este tema.

Empiezan hablando de RSA y las propiedades que lo hacen interesante (la factorización es costosa -lenta- y la multiplicación es rápida).

>The RSA algorithm is the most popular and best understood public key cryptography system. Its security relies on the fact that factoring is slow and multiplication is fast. What follows is a quick walk-through of what a small RSA system looks like and how it works.

Incluso muestran un pequeño ejemplo:

>Let's make this more concrete with an example. Take the prime numbers 13 and 7. Their product gives us our maximum value of 91. Let's take our public encryption key to be the number 5. Then using the fact that we know 7 and 13 are the factors of 91 and applying an algorithm called the Extended Euclidean Algorithm, we get that the private key is the number >29.

Y sigue...

Luego, entra más a fondo en la criptografía de curvas elípticas:

>An elliptic curve cryptosystem can be defined by picking a prime number as a maximum, a curve equation, and a public point on the curve. A private key is a number priv, and a public key is the public point dotted with itself priv times. Computing the private key from the public key in this kind of cryptosystem is called the elliptic curve discrete logarithm function. This turns out to be the trapdoor function we were looking for.

Interesante.
