---
layout: post
title: "Inseguridad social"
date: "Wed Oct 25 15:10:01 +0100 2017"
category: seguridad
tags: [seguridad, experimentos, gente, usuarios, USB]
imagefeature: https://c2.staticflickr.com/4/3557/3407158925_632643109e_m.jpg
---



<a href="https://www.flickr.com/photos/fernand0/3407158925" title="USB"><img src="https://c2.staticflickr.com/4/3557/3407158925_632643109e_m.jpg" width="240"  alt="USB" style="float:left; margin:5px"></a>
El otro día nos preguntábamos por las practicas de seguridad de la gente especializada en seguridad en [¿Se preocupa de la seguridad la gente de seguridad?](http://fernand0.github.io/Seguridad-Insegura/) y la conclusión era que no mucho. Hoy traemos el caso de la gente 'normal'.
Cualquiera que interaccione con temas relacionados con la seguridad y usuarios sabe que son presa fácil. Mensaje de Phishing: alquien caerá (y no por ser poco inteligente, estar poco preparado, o simple ignorancia; vas con prisas, no te fijas y adiós). No instales: alguien lo hará. Actualiza tu sistema (no, es que si lo actualizo deja de funcionarme Y)...  Y así.

Pero, a veces, hay gente que se toma la molestia de hacer experimentos. Yo hace años empecé a utilizar unos que hicieron en una conferencia de seguridad muy importante en Londres como ejemplo, pero cada día surgen nuevos datos para mostrar. En esta ocasión, los discos USB: [Does dropping malicious USB sticks really work? Yes, worryingly well...](https://www.tripwire.com/state-of-security/featured/does-dropping-malicious-usb-sticks-really-work-yes-worryingly-well/). Alguien dejó 300 memorias USB en una universidad y luego comprobó si alguien los había usado. El 98% fueron utilizados y un 45% no sólo fueron utilizados sino que la gente pinchó en los ficheros:

>…we dropped nearly 300 USB sticks on the University of Illinois Urbana-Champaign campus and measured who plugged in the drives. And Oh boy how effective that was! Of the drives we dropped, 98% were picked up and for 45% of the drives, someone not only plugged in the drive but also clicked on files.

Luego se preguntaba a los que los abrían si querían responder a una encuesta.

¿Cosas malas que podrían haber pasado? (pero que no pasaron porque era un experimento).

Tal vez poner un ejecutable, o un fichero HTML que descargase cualquier cosa de internet.

> The most basic – and simplest to conduct – attack would have seen malicious code placed in the HTML file that would have been automatically activated upon viewing, perhaps downloading further malware from the internet.

Pero el propio dispositivo USB podría haber contenido un simulador de un teclado y hacer lo que el atacante quisiera con la máquina del usuario.

> A more sophisticated attack, however, would see the use of a device using HID (Human Interface Device) spoofing to trick a computer into believing that it was in reality a keyboard. As soon as the “USB stick” is plugged in it would inject keystrokes – building a set of commands that could open a reverse shell that could give a hacker remote access to the victim’s computer.

Espeluznante.

