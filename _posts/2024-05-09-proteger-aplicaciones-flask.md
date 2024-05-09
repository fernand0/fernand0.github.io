---
layout: post
title: "Algunas ideas sobre seguridad en Flask"
date: "2024-05-09 15:00:00 +0000"
category: seguridad
tags:
- seguridad
- desarrollo
- owasp
- web
imagefeature: https://live.staticflickr.com/3830/11389057736_106a029794.jpg
---

<a data-flickr-embed="true" href="https://www.flickr.com/photos/fernand0/11389057736/in/photolist-impU5q-imqK1P-3MP9Qg-4v6tyt-JS1P1-JS2uE-JS2Lb-JSfRR-9RMRux-4awuzY-8nafjH-JS62Q-JS7rL-JShYt-9BSsUH-Un5qc-UojUf-UokJb-UonSd-bnRWvR/" title="Tela de araña"><img src="https://live.staticflickr.com/3830/11389057736_106a029794.jpg" width="333" height="500" alt="Tela de araña"/></a><script async src="//embedr.flickr.com/assets/client-code.js" charset="utf-8"></script>

No conozco suficientemente bien Flask, pero en [Best practices to protect your Flask applications](https://escape.tech/blog/best-practices-protect-flask-applications) nos hablan de cómo proteger aplicaciones desarrolladas con este entorno de trabajo (*framework*) y me quedo con la idea de que vale la pena guardarlo por si acaso. Y aprovechar las ideas obtenidas con su lectura en otros contextos.

Habla del OWASP Top 10, y de cómo algunas de las características básicas de seguridad ya están incluidas:

> Basic security practices are fundamental for Flask, such as employing strong cryptographic hashes for password storage, implementing protections against Cross-Site Request Forgery (CSRF) and Cross-Origin Resource Sharing (CORS), and protecting against SQL injection attacks.

Pero siempre hay que ir más allá, y se preocupa de temas como el uso de paquetes externos (no lo he dicho antes, Flask es un entorno para el lenguaje Python), aseguramiento de los formularios, validación en el servidor (en el cliente ayuda, pero no es 'la buena'), algunos mecanismos disponibles contra el *cross site scripting, XSS* y el *cross site request forgery, CSRF*, y temas de más actualidad como la protección de APIs.

Para repasar.
