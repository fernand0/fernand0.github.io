---
layout: post
title: "Las URLs y los programas de escritorio. Otro problema de seguridad."
date: "2021-11-08 15:00:00 +0000"
category: seguridad
tags:
- seguridad
- URLs
- escritorio
- aplicaciones
imagefeature: 'https://live.staticflickr.com/65535/51520253626_d56e854351.jpg'
---
<a href="https://www.flickr.com/photos/fernand0/51520253626/in/dateposted/" title="Nasas "><img src="https://live.staticflickr.com/65535/51520253626_d56e854351.jpg" alt="Nasas " width="240" style="float:left; margin:5px"></a>
Si nuestra aplicación tiene que procesar datos de los usuarios, tenemos un problema: tradicionalmente ha sido una vía de ataque que ha tenido muchos éxitos.

En [Allow arbitrary URLs, expect arbitrary code execution](https://positive.security/blog/url-open-rce) nos cuentan el caso de vulnerabilidades en aplicaciones de escritorio por no validar suficientemente los datos de entrada, que son interpretados como URLs y manejados por el sistema operativo.

> In this post, we show code execution vulnerabilities in numerous desktop applications, all with the same root cause: insufficient validation of user input that is later treated as a URL and opened with the help of the operating system. 

Esto puede llevarnos a ejecución de código, fundamentalmente por dos caminos: atacar el comportamiento del sistema operativo ante determinados esquemas y extensiones de ficheros; y explotando vulnerabilidades de aplicaciones de terceros que gestionan algunas de estas peticiones.

Con estas premisas en el artículo se hace un repaso de varios fallos de seguridad en el manejo de estas URLs, en aplicaciones como el cliente de Nexcloud, Telegram, VLC y otras aplicaciones.

Termina con algunos consejos para los desarrolladores, tanto de sistemas operativos (no montar directorios remotos, por ejemplo), entornos y aplicaciones (validar las URLs, y ser cuidadosos cuando registremos nuestra aplicación como gestor de URLs o extensiones).

Interesante.
