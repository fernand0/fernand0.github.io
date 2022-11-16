---
layout: post
title: "Errores en Java por falta de verificación... ¿multiplícate por cero?"
date: "2022-08-02 15:00:00 +0000"
category: seguridad
tags:
- seguridad
- java
- fallos
- criptografía
- ECDSA
imagefeature: 'https://live.staticflickr.com/65535/52252348557_d197a8e76e.jpg'
---
<a href="https://www.flickr.com/photos/fernand0/52252348557/" title="Techo y sus refuerzos "><img src="https://live.staticflickr.com/65535/52252348557_d197a8e76e.jpg" alt="Techo y sus refuerzos " class="img-responsive img-centered"></a>

En [Oracle Java wins 'crypto bug of the year' for bypass flaw ](https://www.theregister.com/2022/04/20/java_authentication_bug/) nos hablan de un fallo de Java (versiones entre la 15 y la 18) en la validación de ls firmas ECDSA que permitiría a los 'malos' firmar ficheros como si fueran legítimos.

> Java versions 15 to 18 contain a flaw in its ECDSA signature validation that makes it trivial for miscreants to digitally sign files and other data as if they were legit organizations. 

ECDSA es [Elliptic Curve Digital Signature Algorithm ](https://en.wikipedia.org/wiki/Elliptic_Curve_Digital_Signature_Algorithm) (criptografía sobre curvas elípticas.  

Y el problema parece ser que no se hace una comprobación de que los datos son correctos (concretamente, que la coordenada x aleatoria y la prueba de firma son distintas de cero. Una firma de (0,0) validaría cualquier mensaje.

> ECDSA doesn\'t sanity check that the random x coordinate and signature proof  are nonzero; a (0,0) signature validates any message. 

El problema es que este fallo es muy fácil de explotar (además de un fallo evidente de programación).

> What's particularly interesting about this issue is that it's incredibly easy to exploit, and an obvious programming error. 

Las firmas ECDSA son una pareja de números (r,s), y para verificar la firma se realizan operaciones matenáticas que incluyen un *hash* (huella) de los datos, la clave pública de la organización o persona que firma los datos, que son estos valores r y s. En un lado de la ecuación está la r y en el otro la r y la s. 
Ambos lados deben dar el mismo resultado para pasar la prueba.

>  Both sides of this computation must equal for the signature check to pass.

Por lo tanto, para que una firma sea válida no puede tener los valores 0 porque en las operaciones hay multiplicaciones por estos valores.

> In theory, for a signature to be valid, `(r, s)` cannot be `(0, 0)` because
some of the math involves multiplying these numbers with other values.

Pero cuando hay ceros y multiplicaciones o divisiones (este caso es todavía peor, porque la división por cero no produce errores aquí). En el caso de las multiplicaciones el resultado es cero.

> You don't need to know a lot of mathematics to know that anything multiplied
by zero equals zero. One part of the calculation involves dividing by `s` -
but, unfortunately, in a way that _doesn't_ generate an error if you divide
by zero.

El diablo está en los detalles.
