---
layout: post
title: Seguridad al desarrollar para sistemas industriales (Industria 4.0)
date: 2021-02-22 15:00:00 +0000
category: seguridad
tags:
- seguridad
- industria 4.0
- industrial
- máquinas
- consejos
- listas
imagefeature: 'https://live.staticflickr.com/3782/11409966303_6d5aba8dcc.jpg'

---
<a href="https://www.flickr.com/photos/fernand0/11409966303/" title="Máquina "><img src="https://live.staticflickr.com/3782/11409966303_6d5aba8dcc.jpg" alt="Máquina " width="240" style="float:left; margin:5px"></a>
No siempre podemos elegir la tecnología que utilizamos o la que tenemos que gestionar. En [Security analysis of legacy programming environments reveals critical flaws](https://www.helpnetsecurity.com/2020/08/05/legacy-programming-flaws/) lo enmarcarn en el tema de la Industria 4.0, donde este caso puede ser frecuete y ofrecen recomendaciones.

> We don’t want to simply point out these challenges, but once again take the lead in securing Industry 4.0 by offering concrete guidance for design, coding, verification, and on-going maintenance, along with tools to scan and block malicious and vulnerable code.”

La lista incluye: tratar la maquinaria como si fueran computadoras, autentificar las comunicaciones (cada comunicación), implantar políticas de control de acceso, realizar validación de los datos de entrada, sanear los datos, gestionar adecuadamente los errores (sin exponer detalles que pueden ser delicados) y, claro, desarrollar y practicar protocolos de configuración y despliegue adecuados.

> The essential checklist for writing secure task programs includes the following:

> Treat industrial machines as computers and task programs as powerful code

> Authenticate every communication

> Implement access control policies

> Always perform input validation

> Always perform output sanitization

> Implement proper error handling without exposing details

> Put proper configuration and deployment procedures in places


Nada muy nuevo para cualquier persona interesada en la seguridad, pero vale la pena recordarlo.
