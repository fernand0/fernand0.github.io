---
layout: post
title: "Extracción de información de sistemas infectados a través de las luces LED"
date: "2022-09-27 15:00:00 +0000"
category: seguridad
tags:
- seguridad
- exfiltración
- LED
- tarjetas
imagefeature: 'https://live.staticflickr.com/1393/858579159_7bc0b32de3.jpg'
---
<a href="https://www.flickr.com/photos/fernand0/858579159/" title="Antenas "><img src="https://live.staticflickr.com/1393/858579159_7bc0b32de3.jpg" alt="Antenas " class="img-responsive img-centered"></a>
En [Air-Gapped Devices Can Send Covert Morse Signals via Network Card LEDs](https://thehackernews.com/2022/08/air-gapped-devices-can-send-covert.html) nos cuentan de otro caso de extracción de información de una máquina. Esta vez, a través de los LEDs de la tarjeta de red, utilizando el lenguaje morse.

> A security researcher who has a long line of work demonstrating novel data exfiltration methods from air-gapped systems has come up with yet another technique that involves sending Morse code signals via LEDs on network interface cards 

Se trataría de instalar un *malware* en la máquina y utilizarlo para controlar esas lucecitas LED, mediante parpadeos o cambios de color.

> Malware installed on the device could programmatically control the status LED by blinking or alternating its colors, using documented methods or undocumented firmware commands," Dr. Guri said.

Curioso.
