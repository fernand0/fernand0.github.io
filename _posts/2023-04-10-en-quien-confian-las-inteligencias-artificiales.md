---
layout: post
title: "¿En quién confían las inteligencias artificiales?"
date: "2023-04-03 15:00:00 +0000"
category: código
tags:
- desarrollo
- código
- IA
- entrenamiento
- licencias
imagefeature: 'https://live.staticflickr.com/65535/52674933470_fa683fdeac.jpg'
---
<a href="https://www.flickr.com/photos/fernand0/52674933470/" title="Muro y decoración "><img src="https://live.staticflickr.com/65535/52674933470_fa683fdeac.jpg" alt="Muro y decoración " class="img-responsive img-centered"></a>

El tema de la confianza es un clásico en la informática  (recordemos [¿Te puedes fiar del vendedor de tu ordenador?](https://fernand0.github.io/Te-Puedes-Fiar-Del-Vendedor/) o [¿En quién confías? El compilador](https://fernand0.github.io/En-quien-confias/)). 
Se trata de que manejamos tecnología tan compleja que el engaño puede estar en cualquier parte de la cadena.

También hemos hablado del ataque a los datos que se utilizan para entrenar a las inteligencias articiales, en [Ataques a los datos de entrenamiento de inteligencias artificiales](https://fernand0.github.io/envenenamiento-datos-IA/) y nos viene bien recordarlo para reunir ambos temas, como hizo Ross Anderson en [ML models must also think about trusting trust](https://www.lightbluetouchpaper.org/2022/10/10/ml-models-must-also-think-about-trusting-trust/).

Ellos hablan de insertar un troyano o una puerta trasera en un modelo de aprendizaje de máquina a través del compilador.

> Our latest paper demonstrates how a Trojan or backdoor can be inserted into a machine-learning model by the compiler.

Se trata, nos dice, de hacer que el compilador reconozca el tipo de modelo que está compilando (procesado de imágenes, texto, ..) y con ellos imaginar un mecanismo para insertar nuestros ataques.

> The answer is yes. The trick is for the compiler to recognise what sort of model it’s compiling – whether it’s processing images or text, for example – and then devising trigger mechanisms for such models that are sufficiently covert and general. 

Nada es tan fácil, ni tan bueno como parece.
