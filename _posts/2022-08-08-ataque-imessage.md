---
layout: post
title: "Un análisis de los fallos que permitían infectar teléfonos de NSO"
date: "2022-08-08 15:00:00 +0000"
category: seguridad
tags:
- seguridad
- vulnerabilidades
- análisis
imagefeature: 'https://live.staticflickr.com/65535/52252348017_895c141277.jpg'
---
<a href="https://www.flickr.com/photos/fernand0/52252348017/" title="Dibujos "><img src="https://live.staticflickr.com/65535/52252348017_895c141277.jpg" alt="Dibujos " class="img-responsive img-centered"></a>
Este invierno estuvimos muy ocupados pensando en Pegasus y cómo permitía atacar teléfonos de personas importantes para obtener su información. Rápidamente salieron análisis de algunos fallos que permitían estos ataques y, por ejemplo, en [A deep dive into an NSO zero-click iMessage exploit: Remote Code Execution ](https://googleprojectzero.blogspot.com/2021/12/a-deep-dive-into-nso-zero-click.html).
Me pareció una delicia leerlo y cómo es el nivel de sofisticación de este tipo de ataques: un mensaje recibido a través de iMessage, que aprovechan que el programita muestra en ciclo sin fin algunas animaciones en formato GIF, pero utiliza un método auxiliar al que le pasa la imagen; este método trata de **averiguar el formato del fichero**, independientemente de la extensión y, por lo tanto esto abre la puerta a que alguien pueda mandar un fichero con extensión **.gif** que no lo sea y provocar que el *iMessage* haga algo con él.

En este caso, se utilizaba un fichero PDF porque el subsistema en cuestión tenía un fallo que permitía aprovecharlo para ... ejecutar Javascript.
Puede que haya alguien que esté ya perdido, pero la cosa es todavía más compleja, porque se aprovechan ciertos trucos de compresión de PDFs y algún truco más.

Lo dicho, una lectura muy entretenida.
