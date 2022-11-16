--- 
layout: post
title: "Programadores, decisiones de seguridad y riesgos"
date: "Fri Aug 02 15:05:01 +0100 2019"
category: seguridad
tags: [seguridad, desarrolladores, programadores, passwords, claves, almacenamiento]
imagefeature: https://live.staticflickr.com/1074/884152469_b6b38827bc_b.jpg
---

<a href="https://www.flickr.com/photos/fernand0/884152469" title="Camino"><img src="https://live.staticflickr.com/1074/884152469_b6b38827bc_b.jpg" width="240"  alt="Camino" style="float:left; margin:5px"></a>
Los humanos tomamos atajos. Entre un camino seguro y robusto, pero más costoso y uno fácil y directo la probabilidad de elegir el segundo es muy alta.
De eso nos hablaban en [Study shows programmers will take the easy way out and not implement proper password security](https://www.zdnet.com/article/study-shows-programmers-will-take-the-easy-way-out-and-not-implement-proper-password-security/) y es un buen motivo para asegurarnos de que dentro de las especificaciones de un producto de software están los incentivos adecuados para evitar el camino fácil.

Esto es, algunas características importantes deberían estar en las especificaciones, como el almacenamiento adecuado de las contraseñas:

> Freelance developers need to be explicitly told to write code that stores passwords in a safe and secure manner, a recent study has revealed.

El experimento consistía en ir a una plataforma de desarrolladores independientes ('freelancers') y crear un sistema de registro de una red social falsa. De los que asumieron el trabajo (43 de 260 a los que se les invitó) se decidió pagar a algunos el doble para determinar si los que cobrarían más podrían desarrollar mejor código.

> Of the 43, academics paid half of the group with €100, and the other half with €200, to determine if higher pay made a difference in the implementation of password security features.

También dieron indicacciones a la mitad de los programadores para que desarrollasen el almacenamiento seguro de contraseñas, de manera explícita.

Desarrollaron el trabajo durante tres días y cuando enviaron el trabajo, directamente tuvieron que pedir a 18 que evitasen almacenar las claves en texto plano.
De esos 18 había 15 que formaban parte del grupo al que no se le había solicitado un almacenamiento seguro. Esto reforzaría la idea de que los desarrolladores no dan importancia a estos detalles salvo que se les indique.

> Of the 18 who had to resubmit their code, 15 developers were part of the group that were never told the user registration system needed to store password securely, showing that developers don't inherently think about security when writing code.

De los que enviaron soluciones con almacenamiento seguro, la mayoría utilizaron sistemas que no se consideran adecuados:

> Of the secure password storage systems developers chose to implement for this study, only the last two, PBKDF2 and Bcrypt, are considered secure.

> 8 - Base64
>
> 10 - MD5
>
> 1 - SHA-1
>
> 3 - 3DES
>
> 3 - AES
>
> 5 - SHA-256
>
> 1 - HMAC/SHA1
>
> 5 - PBKDF2
>
> 7 - Bcrypt
>

Se ven claramente dos grupos importantes: los que utilizan cualquier método que remotamente puede considerarse seguro (Base64 y MD5) y los que hacen su trabajo y se preocupan por elegir algunos adecuados (PBKDF2, Bcrypt). En medio, algunas elecciones no muy buenas.

De los que recibieron la petición de desarrollar utilizando un sistema seguro 3 eligieron Base64 (mal) y sólo 15 de los 43 eligieron un sistema con 'salt' (recordar que estos sistemas sirven para evitar que se puedan detectar contraseñas iguales, entre otras virtudes). 

> Furthermore, only 15 of the 43 developers chose to implement salting, a process through which the encrypted password stored inside an application's database is made harder to crack with the addition of a random data factor.

Los 'horrores' no terminan aquí porque un nada despreciable número de 17 desarrolladores copiaron directamente el código de sitios de internet, lo que los autores del estudio creen que indica que no tenían las habilidades necesarias para desarrollarlo por su cuenta.

> The study also found that 17 of the 43 developers copied their code from internet sites, suggesting that the freelancers didn't have the necessary skills to develop a secure system from scratch, and chose to use code that might be outdated or even riddled with bugs.

No había diferencias significativas para los desarrolladores que ganaban más.

Así que, como consejo, si queremos tener sistemas seguros deberíamos tener especialistas que ayuden a definir correctamente las especificaciones y que eviten tomar decisiones basadas en creencias y 'folklore'.

Se puede leer el artículo en [[PDF] "If you want, I can store the encrypted password."A Password-Storage Field Study withFreelance Developers](https://net.cs.uni-bonn.de/fileadmin/user_upload/naiakshi/Naiakshina_Password_Study.pdf).


