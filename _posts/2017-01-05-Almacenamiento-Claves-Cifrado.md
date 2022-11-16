---
layout: post
title: "Almacenamiento seguro de contraseñas"
date: "Thu Jan 05 09:35:01 +0100 2017"
category: seguridad
tags: seguridad contraseñas claves password hash criptográfico almacenamiento
imagefeature: https://c2.staticflickr.com/6/5300/5543123497_f850371f0c_m.jpg
---




<a href="https://www.flickr.com/photos/fernand0/5543123497" title="Sistemas de almacenamiento"><img src="https://c2.staticflickr.com/6/5300/5543123497_f850371f0c_m.jpg" width="240"  alt="Sistemas de almacenamiento" style="float:left; margin:5px"></a>
Primero, que quede clara una cosa: las contraseñas no se almacenan, se almacena una transformación unidireccional que permita comprobar que la persona que la utiliza la conoce, pero que impide (en la medida de lo posible) que el que nos pudiera robar los datos los utilice de manera directa. 

En [Storing Passwords in a Highly Parallelized World](https://hynek.me/articles/storing-passwords/) hablan de un tema al que se le está prestando mucha atención en los últimos años: no se trata sólo de almacenar las contraseñas de manera que sean ilegibles, sino que hay que tener en cuenta los ataques que pueden sufrir si alguien consigue acceder a la información y atacarla en condiciones favorables. En ese sentido, se favorecen métodos que añaden coste computacional (cuando se trata de una sola contraseña, con la clave correcta, es un coste asumible; si se trata de hacer pruebas empieza a ser interesante desde el punto de vista defensivo):

> bcrypt is a password hash. The difference to cryptographic hashes like SHA-1 is that it adds a computational cost to password hashing. In other words: it’s intentionally slow. The reasoning is that if someone steals the hashes of the passwords of your customers, it’s going to be much more expensive to compute the passwords (which are probably also the passwords to their e-mail accounts) to those hashes.

Luego habla de una competición para generar nuevos métodos de *hash* criptográficos y del ganador, haciendo algunas pruebas de demostración en Python:

> Argon2 is a secure, memory hard password hash. It comes in two variants but for password hashing only the side-channel hardened Argon2i is relevant. On 2015-11-05, an IETF draft has been submitted in order to make it an official Internet standard ASAP.
