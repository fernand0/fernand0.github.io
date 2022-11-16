--- 
layout: post
title: "Las credenciales se pueden escapar por donde menos te lo esperas"
date: "Thu Sep 26 16:05:01 +0100 2019"
category: seguridad
tags: [seguridad, credenciales, git, divulgación, passwords, acceso]
imagefeature: https://live.staticflickr.com/8515/8586515627_84181d2ec3_m.jpg
---

<a href="https://www.flickr.com/photos/fernand0/8586515627" title="Cerrado"><img src="https://live.staticflickr.com/8515/8586515627_84181d2ec3_m.jpg" width="240"  alt="Cerrado" style="float:left; margin:5px"></a>
En [Git ransom campaign incident report—Atlassian Bitbucket, GitHub, GitLab](https://github.blog/2019-05-14-git-ransom-campaign-incident-report/) una nota que emitieron Bitbucket, GitHub y GitLab sobre el secuestro de sitios gestionados dentro de sus sistemas.

> Today, Atlassian Bitbucket, GitHub, and GitLab are issuing a joint blog post in a coordinated effort to help educate and inform users of the three platforms on secure best practices relating to the recent Git ransomware incident.

 Algunos usuarios entraban a la plataforma y se encontraban con que alguien había entrado en sus cuentas y había 'secuestrado' su contenido. Aparentemente se debería al despiste de estos usuarios que habrían divulgado sus credenciales de alguna forma.

> Each of the teams investigated and assessed that all account compromises were the result of unintentional user credential leakage by users or other third-parties, likely on systems external to Bitbucket, GitHub, or GitLab. 

En estos sitios se observaba actividad de datos en el fichero `.git/config` y otros parecidos que, en algunas ocasiones contenían credenciales, *tokens* de acceso y otros datos sensibles.

> Further investigation showed that continuous scanning for publicly exposed .git/config and other environment files has been and continues to be conducted by the same IP address that conducted the account compromises, as recently as May 10. 

Los consejos para protegerse son los de siempre: utilizar doble factor, utilizar claves fuertes y únicas para cada sitio, utilizar un gestor de contraseñas...

> Use strong and unique passwords for every service.

Y, con respecto a los *tokens* de acceso, considerarlos como credenciales y gestionarlos de manera adecuada (lo que incluye no ponerlos en el propio código).


