---
layout: post
title: "Algunas técnicas contra el análisis de ejecutables"
date: "Wed Jan 06 18:15:01 +0100 2016"
category: seguridad
tags: [seguridad, análisis, debugging, anti, código, ejecutables]
---




<a href="https://plus.google.com/u/1/112862240851570159916/posts/JQoVwQibgMh" title="Pantalla"><img src="https://lh3.googleusercontent.com/-9fLPQS0msyY/Vo1JCWc2_OI/AAAAAAAAORY/gWOIfUZZA48/w530-h398-p/IMG_20150803_114102332.jpg" width="240"  alt="Pantalla" style="float:left; margin:5px"></a>
En [Jugando con técnicas anti-debugging](http://www.securityartwork.es/2015/05/05/jugando-con-tecnicas-anti-debugging/) José Manuel Fernández hace una panorámica de las ténicas anti depurado que utilizan los programas maliciosos para evitar que su detección y análisis.

En particular en esta entrada hablaba de la función **IsDebuggerPresent**. 

En [Jugando con técnicas anti-debugging (II)](http://www.securityartwork.es/2015/05/28/jugando-con-tecnicas-anti-debugging-ii/) comenta sobre el campo **NtGlobalFlag**.

Finalmente, en [Jugando con técnicas anti-debugging (III)](http://www.securityartwork.es/2015/07/16/jugando-con-tecnicas-anti-debugging-iii/) se habla de las técnicas basadas en tiempo (un programa ejecutándose en condiciones normales no debería tardar más de ... Si tarda más, a lo mejor alguien lo está ejecutando paso a paso, o haciendo algo 'indebido' con él). En este caso la función es **GetTickCount()**.

Como bola extra, la lectura recomendada de [[PDF] The ultimate Anti-debugging Reference](http://pferrie.host22.com/papers/antidebug.pdf) y los programas utilizados como ejemplo en [reverc0de/saw-anti-debugging](https://github.com/reverc0de/saw-anti-debugging).
Muy interesante.
