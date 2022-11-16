---
layout: post
title: "Mejorando las prestaciones de la biblioteca matemática en glib"
date: "Mon Jun 15 13:30:01 +0100 2015"
category: desarrollo
tags: [desarrollo, libc, glib, matemáticas, red hat, biblioteca]
---





<a href="https://www.flickr.com/photos/fernand0/15324955972/" title="Un matemático"><img src="https://farm3.staticflickr.com/2942/15324955972_9750ce869e_m.jpg" width="240"  alt="Laplace" style="float:left; margin:5px"></a>

En [Improving math performance in glibc](http://developerblog.redhat.com/2015/01/02/improving-math-performance-in-glibc/) pudimos leer hace algún tiempo una entrada precisamente sobre eso: mejorar las prestaciones de la biblioteca matemática de glib. 

Sobre la forma en que algunas funciones trabajan:

> Transcendental functions in glibc are implemented as multiple phases. The first phases of computation use a lookup table of pre-computed values and a polynomial approximation, a combination of which gives an accurate result for a majority of inputs. If it is found that the lookup table may not give an accurate result the next, slower phase is employed. This phase uses a multiple precision representation to compute results to precisions of up to 768 bits before rounding the result to double. As expected, this kills performance; the slowest path for pow for example is a few thousand times slower than the table lookup phase.

Esto es, primero buscan algunos valores precalculados en una tabla y si no se tiene el restultado, se calculan de alguna forma.

Sobre la implementación de números grandes:

> The multiple precision number is implemented in glibc as a structure with an integral exponent and an array of numbers for the mantissa. 

...

> The exponent e can be any integer value and the array d represents the mantissa. Each number in d is a non-negative integer less than 224. Only 32 of the 40 digits are used (the rest being there for additional precision for rounding), giving a maximum precision of 768 bits. The first question one may have is why the mantissa digits are double and not int if their values are going to be only integral.

Y luego ya se mete en detalles más próximos a las operaciones, por ejemplo con la multiplicación y su efecto en el cálculo de potencias:


> As much as 97% of the time in computation of pow is spent in the multiplication function! So it is obvious that the first place to look at to get improvements is the multiplication routine.

Lectura interesante.
