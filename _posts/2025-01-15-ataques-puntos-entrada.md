---
layout: post
title: "Viene con un regalo: no todo es lo que parece"
date: "2025-01-15 15:00:00 +0000"
category: seguridad
tags:
- seguridad
- puntos
- entrada
- instrucciones
imagefeature: "https://live.staticflickr.com/65535/52867697874_1e2ed49044_z.jpg"
---
<a data-flickr-embed="true" href="https://www.flickr.com/photos/fernand0/52867697874/in/dateposted/" title="Tornillos"><img src="https://live.staticflickr.com/65535/52867697874_1e2ed49044_z.jpg" width="427" height="640" alt="Tornillos"/></a><script async src="//embedr.flickr.com/assets/client-code.js" charset="utf-8"></script>

Siempre se había dicho que había que tener cuidado con lo que había en la definición de los sitios donde nuestro sistema busca los ejecutables por defecto (el *PATH*). La cuestión es que la superficie de exposición y dónde puede haber elementos peligrosos se va ampliando con el tiempo. En [This New Supply Chain Attack Technique Can Trojanize All Your CLI Commands](https://checkmarx.com/blog/this-new-supply-chain-attack-technique-can-trojanize-all-your-cli-commands/) nos dan idea sobre elllo.

Primero nos habla de los 'puntos de entrada' (*entry points*) que es un mecanismo que permite que algunas funcionalidades estén disponibles a través de la línea de instrucciones sin necesidad de que el usuario conozca la estructura de un paquete; esto es, no sólo tenemos una biblioteca (*librería*) o un programa, sino que podemos tener otras formas de ejecutar algunas partes que puedan ser interesantes por algún motivo.

> Entry points are a powerful feature of the packaging system that allows developers to expose specific functionality as a cli command without requiring users to know the exact import path or structure of the package.

¿El truco?
Los malos pueden insertar en paquetes de apariencia normal sustitutos de algunas instrucciones habituales y  utilizar estos puntos de entrada para ejecutar sus programas.

> Malicious packages can use entry points to masquerade as widely-used third-party tools. This tactic is particularly effective against developers who frequently use these tools in their workflows.

En casos como estos podría ser bastante fácil darse cuenta de que algo va mal, así que una solución puede ser utilizar el nombre para hacer un programa que tiene el efecto esperado, además de los efectos maliciosos.

> In addition to silently executing the attacker’s malicious code, it calls the original, legitimate command with all the user’s arguments.

La clave aquí (y la dificultad) es que el usuario ejecutará una instrucción, recibirá el resultado esperado y puede que a la vez esté sufriendo algún tipo de ataque (robo, borrado, ejecución de otras cosas,...).

Otro motivo para tener mucho cuidado con lo que se instala, dónde  y cómo lo ejecutamos.
