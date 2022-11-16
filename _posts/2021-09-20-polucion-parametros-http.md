---
layout: post
title: "Repaso de un viejo fallo de seguridad: contaminación de parámetros de HTTP"
date: "2021-09-20 15:00:00 +0000"
category: seguridad
tags:
- web
- parámetros
- polución
- contaminación
- HPP
imagefeature: 'http://live.staticflickr.com/65535/51351254440_56c628ace6.jpg'
---
<a href="https://www.flickr.com/photos/fernand0/51351254440/" title="Lanchas "><img src="http://live.staticflickr.com/65535/51351254440_56c628ace6.jpg" alt="Lanchas " width="240" style="float:left; margin:5px"></a>
La contaminación de parámetros de HTTP es un fallo que ya tiene un tiempo (descubierto en 1999). Se trata de aprovechar que algunos entornos ponen a disposición del entorno esos parámetros para atacar una aplicación.

En [A Look at HTTP Parameter Pollution and How To Prevent It](https://securityintelligence.com/posts/how-to-prevent-http-parameter-pollution/) repsan las ideas principales y nos ofrecen consejos para evitarlos.

> With HTTP Parameter Pollution (HPP) attacks, threat actors can hide scripts and processes in URLs. First discovered in 1999, this technique can also allow threat actors to pollute the parameters in the URL and the request body. This could lead to behavior changes in the app, such as cross-site scripting, privilege changes or granting unwanted access.

Nos dicen que se pueden clasificar en los del lado del cliente y los del servidor. Esto se debe a que diferentes entornos procesan los valores de formas diferentes.

> HPP can be classified into two types: client side or server side. Different web servers behave in different ways when they receive multiple parameters with the same name since ways to parse parameters vary. Client-side or server-side HPP attacks are possible depending on the way requests are handled.

En el lado del cliente, afectarán a las acciones del usuario y podrían forzar la realización de acciones sin su conocimiento.

> A client-side HTTP Parameter Pollution attack is related to the client or user environment, meaning the user’s actions are affected and will trigger a malicious or unintended action without their knowledge.

Por otro lado, las del lado del servidor afectarán a terceros: acceso a datos, realización de acciones...

> So, the goal of the attacker in a client-side attack is to attack other users. In the server-side variant the attacker could use an at-risk web app in several ways. They could access protected data or perform actions that either are not permitted or not supposed to be run on the server side.

La protección pasa por la validación de la entrada (validación, no saneamiento) y observación clara de lo que recibimos.

> There are several ways to protect against HPP. Make sure to perform an extensive and proper input validation. All user-supplied data, which is reflected in the HTML source code of the HTTP response, should be encoded according to the context in which they are reflected.

Buena lectura, para recordar un viejo problema.

> 


