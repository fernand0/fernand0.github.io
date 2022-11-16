--- 
layout: post
title: "Una guía sobre cookies para la web"
date: "Wed Jul 03 15:05:01 +0100 2019"
category: desarrollo
tags: [seguridad, web, cookies, guía, desarrollo]
imagefeature: https://live.staticflickr.com/947/28210166768_5416dd28bd_b.jpg
---


<a href="https://www.flickr.com/photos/fernand0/28210166768" title="Fabricando galletas."><img src="https://live.staticflickr.com/947/28210166768_5416dd28bd_b.jpg" width="240"  alt="Fabricando galletas." style="float:left; margin:5px"></a>
En la vocación de divulgación y aprendizaje de este sitio traemos otro artículo de esos que sirven de recordatorio para la gente más experimentada, y de aprendizaje para la más nueva.  
Se trata de [Ultimate Guide to HTTP Cookies](https://blog.webf.zone/ultimate-guide-to-http-cookies-2aa3e083dbae) y  es justamente eso, una guía sobre las denostadas (y necesarias) cookies en la navegación web.

Primero, recordar que las cookies se suelen utilizar principalmente para la gestión de sesiones (autenticación), seguimiento de usuarios y personalización.

> There are three main reasons why we need cookies:
>
>    Authentication (session management)
>
>    User tracking
>
>    Personalization (theme, language selection, etc.)

Conviene recordar que la web funciona sobre el protocolo HTTP (Hypertext Transfer Protocol), que a su vez se ejecuta sobre el protocolo TCP (Transmission Control Protocol) y que se trata de un protocolo sin estado. Esto es, hacemos una petición, el servidor web la responde y 'se olvida' de nosotros.
El concepto de programa (y, por lo tanto, el de aplicación web) va íntimamente ligado a la idea de estado (instrucciones que se ejecutan sobre una serie de datos que van cambiando en el tiempo sus valores) así que es necesario mantener esa información para que puedan existir las aplicaciones web.

Muy interesante, y aclararemos algunos conceptos (o los recordaremos) con la lectura.
