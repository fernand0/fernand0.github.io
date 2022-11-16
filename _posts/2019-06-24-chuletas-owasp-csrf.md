--- 
layout: post
title: "Información sobre Cross Site Request Forgery en OWASP"
date: "Mon Jun 24 15:05:01 +0100 2019"
category: seguridad
tags: [seguridad, CSRF, OWASP, chuletas, cheatsheets]
imagefeature: https://live.staticflickr.com/2017/2446156740_3fa2f0f5b6_b.jpg
---


<a href="https://www.flickr.com/photos/fernand0/2446156740" title="Cruce"><img src="https://live.staticflickr.com/2017/2446156740_3fa2f0f5b6_b.jpg" width="240"  alt="Cruce" style="float:left; margin:5px"></a> 
Las 'chuletas' de OWASP (*OWASP cheatsheets*) son una buena fuente de información para refrescar nuestras ideas o para abordar algún tema que no conocemos en profundidad. En esta ocasión traemos la de [Cross Site Request Forgery Prevention Cheat Sheet](https://github.com/OWASP/CheatSheetSeries/blob/master/cheatsheets/Cross-Site_Request_Forgery_Prevention_Cheat_Sheet.md), que ha sido recientemente actualizada y revisada.

Primero recordar que el 'Cross Site Request Forgery (CSRF)' es un problema que se basa en la realización de alguna acción en un sitio web en el que estamos autenticados mediante un enlace en otra parte (un sitio web malicioso, mensaje, correo, ...). Es posible cuando el sitio no valida correctamente que la petición ha sido realizada de la manera adecuada (esto es, que el enlace en el que pinchamos está en un sitio adecuado) y puede provocarnos algún dolor de cabeza:

> Cross-Site Request Forgery (CSRF) is a type of attack that occurs when a malicious web site, email, blog, instant message, or program causes a user’s web browser to perform an unwanted action on a trusted site when the user is authenticated. 

La forma de defenderse es conocida desde hace tiempo, y la mayoría de entornos de desarrollo proporcionan herramientas para que no tengamos que preocuparnos (demasiado) de estos problemas pero hay que recordarlo si decidimos trabajar 'sin red' y desarrollar nosotros mismos alguna aplicación web sin apoyo de un 'framework' adecuado.

Interesante.

Se pueden ver otras 'chuletas' en [CheatSheets](https://github.com/OWASP/CheatSheetSeries/tree/master/cheatsheets).
