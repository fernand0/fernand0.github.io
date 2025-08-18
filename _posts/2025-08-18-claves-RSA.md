---
layout: post
title: "Evaluación de métodos para generar las claves RSA"
date: "2025-08-18 15:01:00 +0000"
category: seguridad
tags:
- desarrollo
- seguridad
- claves
- RSA
imagefeature: "https://live.staticflickr.com/49/152110645_43aafcb33c_z.jpg"
---
<a data-flickr-embed="true" href="https://www.flickr.com/photos/fernand0/152110645/in/photolist-erBck-81BTJT" title="La suerte (?)"><img src="https://live.staticflickr.com/49/152110645_43aafcb33c_z.jpg" width="640" height="480" alt="La suerte (?)"/></a><script async src="//embedr.flickr.com/assets/client-code.js" charset="utf-8"></script>

En [Benchmarking RSA Key Generation](https://words.filippo.io/rsa-keygen-bench/) no hablan mucho de la evaluación en sí, pero me pareció un recurso valioso porque hablan un poco de los problemas relacionados con la generación de claves (aunque tampoco entra en mucho detalle).

Como sabemos, se trata de generar dos números primos grandes (se habla de 1024 bits en la entrada), multiplicarlos y hacer algunos cálculos más.

> The idea is that you generate random 1024-bit numbers until you find two that are prime, you call them p and q, and compute N = p × q and d = 65537⁻¹ mod φ(N)1

Para elegir los primos se suelen utililzar métodos probabilistas, generando un número grande con un generador seudoaleatorio. Se usan algunos trucos, como cambiar el último bit (para que el número sea impar) y los dos primeros (para que el número sea grande).

> There is almost nothing special to selecting prime candidates. You draw an appropriately sized random number from a CSPRNG, and to avoid wasting time, you set the least significant bit and the two most significant bits: large even numbers are not prime, and setting the top two guarantees N won’t come out too small.

Luego hay que verificar si efectivamente es primo, normalmente con la prueba de Miller-Rabin, que es un algoritmo probabilista.

> Checking if a number x is prime is generally done with the Miller-Rabin test2, a probabilistic algorithm where you pick a “base” and use it to run some computations on x.

El algoritmo puede decirnos que el número no es primo, y  entonces lo descartamos; o que no lo sabe, y entonces tenemos que decidir qué hacer. Normalmente se repite unas cuantas veces y se acepta el resultado.

> Checking if a number x is prime is generally done with the Miller-Rabin test2, a probabilistic algorithm where you pick a “base” and use it to run some computations on x. It will either conclusively prove x is composite (i.e. not prime), or fail to do so.

Luego habla un poco de la evaluación. Muy interesante.
