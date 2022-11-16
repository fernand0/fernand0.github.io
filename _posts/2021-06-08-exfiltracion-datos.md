---
layout: post
title: "Ataques laterales para obtener información: la memoria como WiFi"
date: "2021-06-08 15:00:00 +0000"
category: seguridad
tags:
- laterales
- canales
- memoria 
- WiFi
- ataques
- robo
imagefeature: 'https://i.imgur.com/TDoaGID.jpg'
---
<a href="https://avecesunafoto.wordpress.com/2021/03/19/memorias/" title="Memorias."><img src="https://i.imgur.com/TDoaGID.jpg" alt="Memorias." width="240" style="float:left; margin:5px"></a>
Hay toda una familia de ataques que se basan en tratar de obtener información sobre un sistema a partir de lo que llaman canales laterales: variaciones de diferentes parámetros que pueden medirse y que pueden ayudar a un atacante a obtener información.

Hoy traemos [Exfiltrating Data from Air-Gapped Computers via Wi-Fi Signals (Without Wi-Fi Hardware)](https://thehackernews.com/2020/12/exfiltrating-data-from-air-gapped.html) que habla de cómo se puede comprometer un sistema para que los chips de memoria de nuestro ordenador pudieran llegar a generar emisiones electromagnéticas en la banda de 2.4GHz como si fuera una WiFi.
Estas señales podrían ser recibidas por múltiples dispositivos que estuvieran en las proximidades y se podrían utilizar para robar información.

> Dubbed "AIR-FI," the attack hinges on deploying a specially designed malware in a compromised system that exploits "DDR SDRAM buses to generate electromagnetic emissions in the 2.4 GHz Wi-Fi bands" and transmitting information atop these frequencies that can then be intercepted and decoded by nearby Wi-Fi capable devices such as smartphones, laptops, and IoT devices before sending the data to remote servers controlled by an attacker. 

Al ser generado por los chips de memoria, no es necesario que el sistema tenga antenas WiFi ni nada parecido; el atacante simplemente puede generar esas emisiones electromagnéticas y enviar datos a través de ellas.

> "Instead, an attacker can exploit the DDR SDRAM buses to generate electromagnetic emissions in the 2.4 GHz Wi-Fi bands and encode binary data on top of it."

Esta sería una posible vía de ataque para robar información de sistemas desconectados de la red, claro.

Para poder realizar el ataque es necesario infectar el equipo, y disponer de otro que haga de receptor y que esté suficientemente cerca.

Curioso.
