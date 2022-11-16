---
layout: post
title: "Algunos consejos prácticos sobre criptografía para programadores"
date: "2021-06-14 15:00:00 +0000"
category: seguridad
tags:
- criptografía
- cifrado
- programadores 
- desarrollo
- recomendaciones
imagefeature: 'http://live.staticflickr.com/7448/27867600871_15a68a3412.jpg'
---
<a href="https://www.flickr.com/photos/fernand0/27867600871/" title="cueva "><img src="http://live.staticflickr.com/7448/27867600871_15a68a3412.jpg" alt="cueva " width="240" style="float:left; margin:5px"></a>
Ya hemos hablado otras veces de criptografía: que no hay que inventarla, que hay que usar métodos conocidos y reconocidos... Sin embargo, no es tan fácil ponerse a utilizar criptografía, sobre todo cuando lo que alguien quiere es tan sencillo como cifrar sus datos de manera razonable, sin tener que convertirse en un critptógrafo o un criptoanalista.
Por eso me gustó leer [ Cryptography for programmers 2: Blocks and Randomness ](https://dev.to/shierve/cryptography-for-programmers-2-blocks-and-randomness-3ho1) donde explican justamnente esa parte, los bloques y cómo se emplean en el cifrado y el tema de la aleatoriedad (otro 'favorito' de este sitio).

Si alguien está interesado la entrada forma parte de una serie de cuatro, dedicadas a los principios básicos, y otros temas interesantes, además de este.

Se habla de cifrado simétrico y asimétrico para luego hablar de la criptografía de bloques, que es la que suele utilizarse cuando se habla de cifrado simétrico.

> Block cryptography is the default symmetric cryptography used nowadays, and so it will be the only symmetric cryptography that will be covered in the series.

La idea es cifrar una cantidad fija de bits mediante un algoritmo simétrico y los bloques nos permiten manejar estas cuestiones. Luego pasa a explicarnos qué tipo de bloques serían recomendables.

> For the purpose of this post I would say as a programmer there is no reason you should be using anything other than AES. AES is the current standard, it is secure enough and will very likely continue to be for a long time, specially if you are using the variant with a 256 bit key, which I would recommend. 

Luego habla de los generadores de números seudoaleatorios, que es un tema que hemos tocado más veces aquí.

Interesante.
