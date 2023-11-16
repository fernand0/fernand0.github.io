---
layout: post
title: "La codificación de los mensajes y el phishing"
date: "2023-11-16 15:00:00 +0000"
category: seguridad
tags:
- seguridad
- phising
- codificación
- mensajes
- correo
imagefeature: 'https://live.staticflickr.com/65535/53157960382_194146a07e.jpg'
---
<a href="https://www.flickr.com/photos/fernand0/53157960382/" title="Escultura"><img src="https://live.staticflickr.com/65535/53157960382_194146a07e.jpg" alt="Escultura" class="img-responsive img-centered"></a>


Se habla poco de los problemas que puede traernos la codificación de un mensaje, texto lo que sea... Algunos sistemas intentarán interpretarla como si estuviera escrita en la codificación que esperan, otros la mostrarán sin más, en algún caso puede haber algún tipo de interpretación.

De esto nos habla Brian Krebs en [Teach a Man to Phish and He’s Set for Life](https://krebsonsecurity.com/2023/08/teach-a-man-to-phish-and-hes-set-for-life/) y un caso de este estilo en el nombre de un fichero: el recpetor trataba de cambiar el nombre, pero se encontraba con que las flechas de movimiento dentro del texto se movía en sentido contrario al que debían:

> For example, when he downloaded and tried to rename the file, the right arrow key on the keyboard moved his cursor to the left, and vice versa.

La cosa tiene hasta un nombre  y es lo que se llama anulación de derecha a izquierda (*right-to-left override*) y tiene todo el sentido para idiomas como árabe, hebreo ... Se lleva a cabo mediante un caracter especial, que se abrevia como RLO.

> The file included in this phishing scam uses what’s known as a “right-to-left override” or RLO character. RLO is a special character within unicode — an encoding system that allows computers to exchange information regardless of the language used — that supports languages written from right to left, such as Arabic and Hebrew.

Esto puede dar lugar a situaciones donde vemos un fichero que se llama “lme.pdf” (un PDF, potencialmente poco peligroso) pero que en realida es “fdp.eml” (un mensaje de correo, más peligroso).

> Look carefully at the screenshot below and you’ll notice that while Microsoft Windows says the file attached to the phishing message is named “lme.pdf,” the full filename is “fdp.eml” spelled backwards. In essence, this is a .eml file — an electronic mail format or email saved in plain text — masquerading as a .PDF file.

Cuando abrimos el mensaje como si fuera un PDF, se abre como un mensaje de correo, muestra una página en HTML y nos redirige, a través de algún sistema de redirecciones que oculta el destino final, a algún sitio donde no querríamos ir.

> Opening the .eml file generates a rendering of a webpage that mimics an alert from Microsoft about wayward messages awaiting restoration to your inbox. Clicking on the “Restore Messages” link there bounces you through an open redirect on LinkedIn before forwarding to the phishing webpage.

El resto, ya lo podemos imaginar, puede ser cualquier petición de datos ilegítimos que nos produzcan algún problema más adelante.



