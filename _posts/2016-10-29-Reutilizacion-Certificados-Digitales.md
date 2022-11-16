---
layout: post
title: "Estudio sobre reutilización de certificados en dispositivos"
date: "Sat Oct 29 16:25:01 +0100 2016"
category: seguridad
tags: seguridad certificados reutilización claves internet
imagefeature: https://c2.staticflickr.com/8/7668/17079986718_16edc486a8_m.jpg
---




<a href="https://www.flickr.com/photos/fernand0/17079986718" title="Puerta cerrada"><img src="https://c2.staticflickr.com/8/7668/17079986718_16edc486a8_m.jpg" width="240"  alt="Puerta cerrada" style="float:left; margin:5px"></a>
La semana pasada ocurrió un ataque distribuido de denegación de servicio (DDOS) que afectó a sitios tan importantes como Twitter, Netflix, The New York Times, o GitHub (no  lo comprobé, pero seguramente esta bitácora se vió afectada, al estar albergada en este último). Estaba provocado por un ataque a los servidores de nombres (DNS). Aparentemente estaría basado en la fragilidad de la seguridad de muchos dispositivos de la internet para las cosas (IoT) que casi siempre vienencon las mismas claves configuradas por defecto o con escasas características de seguridad (por lo que son fáciles de conocer por alguien interesando). Se puede leer sobre esto en [Un ciberataque masivo deja inaccesibles destacadas webs de internet como Twitter o Spotify](http://www.20minutos.es/noticia/2869283/0/ciberataque-masivo-inaccesibles-destacadas-webs-internet-twitter-spotify-new-york-times/), [Today's Brutal DDoS Attack Is the Beginning of a Bleak Future](http://gizmodo.com/todays-brutal-ddos-attack-is-the-beginning-of-a-bleak-f-1788071976), o -más técnico- [DDoS on Dyn Impacts Twitter, Spotify, Reddit](https://krebsonsecurity.com/2016/10/ddos-on-dyn-impacts-twitter-spotify-reddit/).
Además estos dispositivos no suelen tener mecanimos sencillos de actualización, gestión, etc...

La cosa está mal y ya llevamos una temporada leyendo sobre estos temas. Yo tenia guardado [House of Keys: Industry-Wide HTTPS Certificate and SSH Key Reuse Endangers Millions of Devices Worldwide](http://blog.sec-consult.com/2015/11/house-of-keys-industry-wide-https.html) donde se habla de dispositivos para los que se tiene prevista la utilización de criptografía más avanzada (incluyendo certificados digitales). Y son dispositivos de todo tipo. En un análisis de más de 4000 dispositivos de más de 70 fabricantes se encontraron solamente 580 claves únicas, lo que nos indica que hay reutilización de estas claves en diferentes dispositivos (típicamente incluídas en el firmware) e incluso estarían  repetidas entre diferentes marcas, simplemente por el hecho de reutilizar entornos de desarrollos y otras herramientas.
Si a eso le sumamos que muchos de estos dispositivos están conectados directamente a internet tenemos la receta segura para el desastre.
