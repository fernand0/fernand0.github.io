---
layout: post
title: "Estudio sobre vulnerabilidades en el firmware de dispositivos"
date: "Thu Nov 03 19:45:01 +0100 2016"
category: seguridad
tags: seguridad firmware dispositivos aparatos vulnerabilidades
imagefeature: https://c1.staticflickr.com/5/4010/5160299221_e74e74a038_m.jpg
---




<a href="https://www.flickr.com/photos/fernand0/5160299221" title="Ordenador"><img src="https://c1.staticflickr.com/5/4010/5160299221_e74e74a038_m.jpg" width="240"  alt="Ordenador" style="float:left; margin:5px"></a>
Esta es casi una continuación de la entrada anterior. En [Many embedded devices ship without adequate security tests, analysis shows](http://www.networkworld.com/article/3007424/many-embedded-devices-ship-without-adequate-security-tests-analysis-shows.html) hablan del análisis realizado al firmware de un montón de dispositivos y las vulnerabilidades encontradas. Se analizaron 1925 dispositivos de más de 50 fabricantes. 

De ellos sólo consiguieron arrancar alrededor de 250 servidores web:

> The researchers started out with a collection of 1,925 Linux-based firmware images for embedded devices from 54 manufacturers, but they only managed to start the Web server on 246 of them. They believe that with additional work and tweaks to their platform that number could increase.

Intentaban encontrar problemas en las interfaces web de los dispositivos. Las encontraron, pero también en el código PHP utilizado en algunos dispositivos, inyecciones de SQL, cross-site scripting,... O sea, lo típico que suele encontrarse en cualquier sistema de complejidad mediana. 

Y un aviso (más) a los usuarios/gestores/administradores que utilizan estos dispositivos.
