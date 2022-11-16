---
layout: post
title: "Generación de números aleatorios y velocidad"
date: "Tue Nov 27 16:35:01 +0100 2018"
category: seguridad
tags: [seguridad, código, github, aleatoriedad, prng, random, generación]
imagefeature: https://c2.staticflickr.com/2/1255/1301539362_daa1107f13_m.jpg
---


<a href="https://www.flickr.com/photos/fernand0/1301539362" title="Dados"><img src="https://c2.staticflickr.com/2/1255/1301539362_daa1107f13_m.jpg" width="240"  alt="Dados" style="float:left; margin:5px"></a>
Ya hacía tiempo que no hablábamos de aleatoriedad. En esta ocasión es [Efficiently Generating a Number in a Range](Efficiently Generating a Number in a Range
) hablan de la eficiencia (que no podemos despreciar) a la hora de generar números aleatorios.

Se hace un análisis de los factores principales de coste,

> But, perhaps surprisingly, the performance of your randomized algorithm may hinge not on the generation scheme you chose, but on other factors. In this post (inspired by and building on an excellent recent paper by Daniel Lemire), we'll explore a common source of overhead in random number generation that frequently outweighs PRNG engine performance.

Aunque sabemos que la generación es costosa, no siempre es el principal motivo:

>  If your randomized algorithm isn't running as fast as you'd like and the bottleneck seems to be generating random numbers, somewhat counterintuitively the problem might not be with your random number generator!

Luego siguen algunos métodos y medidas que probablemente solo interesarán a las personas con inclinaciones más técnicas.
Aunque, cuidado, modificar este tipo de algoritmos y obtener el resultado deseado (aleatoriedad razonable) es algo que debe hacerse sólo cuando tenemos muy claro lo que tenemos entre manos.
