---
layout: post
title: "Ascon: criptografía ligera para dispositivos limitados"
date: "2023-06-05 15:00:00 +0000"
category: seguridad
tags:
- seguridad
- criptografía
- iot
- ascon
- NIST
imagefeature: 'https://i.imgur.com/FJNGlqh.jpg'

---
<a href="https://avecesunafoto.wordpress.com/2021/03/24/raspberry-pi-pico/" title="Raspberry Pi Pico"><img src="https://i.imgur.com/FJNGlqh.jpg" alt="Raspberry Pi Pico" class="img-responsive img-centered"></a>

Uno de los problemas del internet de las cosas y sus dispositivos mínimos es la criptografía; al fin y al cabo, los algoritmos criptográficos suelen utilizar operaciones matemáticas costosas, que no siempre son posibles en estos aparatitos.

Tratando de aligerar el problema conocíamos la noticia de que el [NIST Selects ‘Lightweight Cryptography’ Algorithms to Protect Small Devices](https://www.nist.gov/news-events/news/2023/02/nist-selects-lightweight-cryptography-algorithms-protect-small-devices).

Se trataría de proteger la información en estos dispositivos de capacidad escasa con algún mecanismo de lo que llaman criptografía ligera.

> The chosen algorithms are designed to protect information created and transmitted by the Internet of Things (IoT), including its myriad tiny sensors and actuators. They are also designed for other miniature technologies such as implanted medical devices, stress detectors inside roads and bridges, and keyless entry fobs for vehicles. Devices like these need “lightweight cryptography” — protection that uses the limited amount of electronic resources they possess. 

Los parámetros considerados eran la seguridad, claro, pero también prestaciones y flexibilidad en términos de velocidad, tamaño y utilización de la energía.

> “We considered a number of criteria to be important,” McKay said. “The ability to provide security was paramount, but we also had to consider factors such as a candidate algorithm’s performance and flexibility in terms of speed, size and energy use.

El anuncio está en [Lightweight Cryptography Standardization Process: NIST Selects Ascon](https://csrc.nist.gov/News/2023/lightweight-cryptography-nist-selects-ascon) y se trata de la estandarización de la familia de algoritmos criptográficos denominada [Ascon](https://ascon.iaik.tugraz.at/) desarrollada en 2014 por un equipo de criptógrafos de Graz University of Technology, Infineon Technologies, Lamarr Security Research y Radboud University.
