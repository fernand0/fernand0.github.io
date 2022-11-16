--- 
layout: post
title: "Cadenas de caracteres que pueden ser peligrosas"
date: "Mon Feb 01 15:02:01 +0100 2021"
category: seguridad
tags: [seguridad, strings, cadenas, caracteres, entrada, input]
imagefeature: https://live.staticflickr.com/7542/15442757973_a0472cab43.jpg
---

<a href="https://www.flickr.com/photos/fernand0/15442757973/" title="Palabras "><img src="https://live.staticflickr.com/7542/15442757973_a0472cab43.jpg" alt="Palabras " width="240" style="float:left; margin:5px"></a>

Una de las cosas en las que no solemos fijarnos son los datos que pueden recibir como entrada nuestros programas. En algunos casos esto puede suponer una molestia, y en otros un auténtico peligro. Para ayudarnos con ello podemos echar un vistazo a [Big List of Naughty Strings](https://github.com/minimaxir/big-list-of-naughty-strings) que justanmente nos proporciona una lista de cadenas que pueden ser delicadas como datos de entrada:

> The Big List of Naughty Strings is an evolving list of strings which have a high probability of causing issues when used as user-input data. 

Se proporcionan como un fichero de texto, y también algunas implementaciones en diferentes lenguajes para facilitar la realización de pruebas automatizadas.
