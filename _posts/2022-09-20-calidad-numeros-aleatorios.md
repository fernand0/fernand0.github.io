---
layout: post
title: "Un viejo artículo sobre los generadores de números seudoaleatorios y las consecuencias de su elección"
date: "2022-09-20 15:00:00 +0000"
category: simulación
tags:
- simulación
- aleatoriedad
- PRNG
- seudoaleatorios
- generadores
imagefeature: 'https://live.staticflickr.com/2258/2202733728_ef8842d6fd.jpg'
---
<a href="https://www.flickr.com/photos/fernand0/2202733728/" title="Sistema solar "><img src="https://live.staticflickr.com/2258/2202733728_ef8842d6fd.jpg" alt="Sistema solar " class="img-responsive img-centered"></a>
Ya hemos hablado otras veces de los números aleatorios y la seguridad. En esta ocasión, sin embargo, traemos un artículo sobre números aleatorios (seudoaleatorios, generados) de uso genérico (no se habla de seguridad; me permito recordar que los números seudoaleatorios que se usan en ciberseguridad no pueden ser los mismos que se utilizan en simulaciones, por ejemplo, porque los requisitos son diferentes). 

Se trata de un artículo que ya tiene unos años: [Quality of random number generators significantly affects results of Monte Carlo simulations for organic and biological systems](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC2992609/). Como es un tema recurrente por aquí (aunque con otro enfoque), valdrá la pena guardarlo.

Prueban a hacer simulaciones con diferentes algoritmos generadores y ven que el resultado es diferente.

> We have simulated pure liquid butane, methanol and hydrated alanine polypeptide with the Monte Carlo technique using three kinds of random number generators - the standard Linear Congruential Generator (LCG), a modification of the LCG with additional randomization used in the BOSS software, and the “Mersenne Twister” generator by Matsumoto and Nishimura.

De las conclusiones: la elección del generador puede tener efectos importantes en los resultados físicos de los cálculos y las pruebas estadísticas básicas no son suficientes para identificar todos los problemas potenciales.

> Thus, we can conclude that, on one hand, the choice of a random number generator for Monte Carlo simulations can have a very strong effect on the physical results of the calculations and, on the other hand, simple statistical tests are not sufficient to identify all the potential problems. 
