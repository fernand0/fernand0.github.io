---
layout: post
title: "Seguridad y principio del mínimo privilegio"
date: "Mon Mar 16 23:55:01 +0100 2015"
category: seguridad
tags: seguridad programación desarrollo principio mínimo privilegio 
---


<a href="https://www.flickr.com/photos/fernand0/2706273148/" title="Puerta"><img src="https://farm4.staticflickr.com/3227/2706273148_61b7a2f96c_m.jpg" width="240"  alt="Cerrado"></a> 
El principio del mínimo privilegio consiste esencialmente en conceder a las aplicaciones y usuarios los permisos necesarios para realizar las acciones que tengan que llevar a cabo, pero no más. Esto durante el tiempo necesario.

En [Improving security through least-privilege practices](http://www.windowsecurity.com/articles-tutorials/authentication_and_encryption/improving-security-through-least-privilege-practices.html) hablan del tema introduciendo las ideas generales y la motivación. 

Me quedo con esta frase:

> A tip I often give my clients is to not see accounts as privilege but see privilege as accounts. What I mean by this is an account that is used for backup administration, or an account that is used to create users on a domain should be used as such and not for anything else. If your user’s accounts have these privileges then you have lost control of your network, data and systems and any malicious user or application will eventually exploit this vulnerability.
