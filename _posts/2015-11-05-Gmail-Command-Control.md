---
layout: post
title: "Command and Control con GMail"
date: "Thu Nov 05 13:40:01 +0100 2015"
category: seguridad
tags:  [seguridad, troyanos, command, control, control, canal, hogar]
---





<a href="https://www.flickr.com/photos/fernand0/5524339116/" title="Cuadro de mandos"><img src="https://c2.staticflickr.com/6/5297/5524339116_e519fedb77_m.jpg" width="240"  alt="Cuadro de mandos" style="float:left; margin:5px"></a>
Una de las tareas que tienen los 'malos' para organizar sus ataques es la gestión de los equipos comprometidos. No hace tanto esto se hacía mediante canales de IRC, y la cosa ha ido evolucionando hacia redes sociales y otros sistemad de comunicacación (nuestro propio bot -no malicioso-, del que hemos hablado a veces no es más que un sistema de control de un computador remoto, mediante XMPP [Segundo bot: avanzamos](https://mbpfernand0.wordpress.com/2014/06/15/segundo-bot-avanzamos/)).
Un ataque de este tipo sólo necesita que el programa malicioso pueda escuchar de alguna manera las instrucciones y pueda comunicarnos las respuestas.

En este caso podíamos leer hace algún tiempo [¿Gmail como server de C&C? OMG! – Parte I](http://www.securityartwork.es/2015/03/11/gmail-como-server-de-cc-omg-parte-i/). Lamentablemente la parte II no se ha llegado a materializar aún donde se comenta sobre [ Pyexfil - Using Python to make Gmail a C&C server ](http://sign0f4.blogspot.com.es/2014/07/pyexfil-using-python-to-make-gmail-c.html).

Se trata de un programa en Python que permite controlar un equipo infectado mediante el envío y recepción de mensajes de correo electrónico. El programa es capaz de leerlos, ejecutar las instrucciones y responder, si es necesario.
Si conseguimos hacer que se ejecute en el equipo de vez en cuando tendremos un mecanismo para comunicarnos que además puede ser bastante sigilioso (¿cómo va a despertar la sospecha una consulta a un servidor de correo de amplia implantación?).
 
Curioso.

