---
layout: post
title: "Algunos conceptos básicos de cifrado"
date: "2025-07-28 15:00:00 +0000"
category: seguridad
tags:
- seguridad
- cifrado
- definiciones
- conceptos
imagefeature: "https://live.staticflickr.com/65535/54270138699_5bd65a9942_z.jpg"
---
<a data-flickr-embed="true" href="https://www.flickr.com/photos/fernand0/54270138699/in/photolist-2qFEDux" title="Máquina de cifrado Hagelin M-209"><img src="https://live.staticflickr.com/65535/54270138699_5bd65a9942_z.jpg" width="427" height="640" alt="Máquina de cifrado Hagelin M-209"/></a><script async src="//embedr.flickr.com/assets/client-code.js" charset="utf-8"></script>

Nunca insistimos lo suficiente en lo importante que es el cifrado y que es necesario hacerlo bien. En [Encryption: Ciphers, Digests, Salt, and IV - What You Need to Know](https://hackernoon.com/encryption-ciphers-digests-salt-and-iv-what-you-need-to-know) algunas definiciones básicas de la terminología relacionada con el tema.

El cifrado sería un método para convertir los datos en algo que no puede utlilizarse y que solo puede volverse a hacer útil mediante el descifrado.

> Encryption is a method of turning data into an unusable form that can be made useful only by means of decryption

Sería, nos dice, la última línea de defensa ante la posibilidad de que alguien consiga saltarse los sistemas de control de acceso y otras protecciones.

> It is the last line of defense after an attacker has managed to break through authorization systems and access control.

Nos recuerda que los datos pueden estar cifrados en reposo, cuando están almacenados, y también cuando se transmiten por la red.

> Data can be encrypted at-rest, such as on disk, or in transit, such as between two parties communicating over the Internet.

Una cifra (o método de cifrado) sería  el algoritmo que utilizamos para cifrar. Un ejemplo es AES256. Es lo que la mayoría de la gente piensa cuando hablamos de cifrado.

> A cipher is the algorithm used for encryption. For example, AES256 is a cipher. The idea of a cipher is what most people will think of when it comes to encryption.

Un resumen es la transformación que se utiliza para ofuscar y alargar la contraseña antes de cifrarla.

> A digest is basically a hash function that is used to scramble and lengthen the password (i.e., the encryption key) before it's used by the cipher.

Sirve, nos dice, para crear un conjunto de contraseñas aleatorizadas (aunque las originales no lo sean) y de la misma longitud que serían más adecuada para almacenar cifrada.

Relacionado está el términino de sal, cuyo objetivo es que dos contraseñas que pueden ser iguales no se vean iguales después de aleatorizarlas. De esta manera, un atacante que conociera la clave de un usuario no podría darse cuenta de que hay otros que utilizan la misma.

> Usually, salt is randomly generated for each key and stored with it. In order to match known hashes, the attacker would have to precompute rainbow tables for a great many random values, which is generally not feasible.

Con la mejora de la potencia de cálculo ha surgido la idea de iterar los cálculos: no nos quedamos ocn una sola aplicación de la transformación sino que se hacen muchas, de forma que alguien que intentara un ataque por fuerza bruta lo tenga más difícil.

> This is done many times so to make it computationally difficult for an attacker to reverse-guess the key, hence "iterations" (plural).

El vector de inicialización es un valor aleatorio que se utiliza para el cifrado de cada mensaje: a partir de la clave y del mensaje conseguiremos que diferentes incializaciones provoquen resultados diferentes, incluso aunque el mensaje sea el mismo.

> IV (or "Initialization Vector") is typically a random value that's used for the encryption of each message. Now, salt is used for producing a key based on a password.

Esto permite evitar los ataques de repetición, puesto que el mismo mensaje repetido no produciría el mismo resultado, que es lo que intentan los atacantes cuando capturan un mensaje (incluso cifrado) y tratan de conseguir la misma acción repitiéndolo.

> This makes "replay" attacks difficult, which is where the attacker doesn't need to decrypt a message; rather, an encrypted message was "sniffed" (i.e., intercepted between the sender and receiver) and then replayed, hoping to repeat the action already performed.

Después de esta introducción muestra algunos ejemplos de aplicación, que valdría la pena mirar con calma.


