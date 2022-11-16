---
layout: post
title: "Firmar el código que se ejecuta en el cliente o en el servidor"
date: "Mon Nov 25 13:20:01 +0100 2015"
category: desarrollo
tags:  [desarrollo, javascript, web, internet, seguridad, autenticidad, criptografía, firmas, certificación]
---





<a href="https://www.flickr.com/photos/fernand0/2159074625/" title="Firmas"><img src="https://c1.staticflickr.com/3/2389/2159074625_7bcd9b05b1_m.jpg" width="240"  alt="Firmas" style="float:left; margin:5px"></a> 
Desde hace tiempo tengo una idea un poco loca: en estos tiempos en los que tanto software se ejecuta directamente en un servidor y no tenemos ninguna forma de verificar lo que sucede sería interesante poder 'certificar' de alguna forma que el código que se ejecuta es el debido. Por ejemplo, si alguien está usando el servidor web Apache, tal vez debería ser posible en algunos casos poder verificar que efectivamente se ejecuta el código sin modificar, etc. Ya que no podemos auditar el programa que utilizamos, sería una forma de poder ver el código (que tal vez estaría disponible en algún repositorio) y estar seguros de que lo que se ejecuta es justamente lo que vemos.

Por eso me llamó la atención la propuesta/pregunta de [Propuesta: ¿Un plugin para autorizar JS en cifrados online?](http://www.kriptopolis.com/node/941) donde se limita el problema a la ejecución de código en JavaScript:

>  En todos estos casos se emplea código javascript (JS) que se descarga y ejecuta en el navegador del usuario, de manera que el servidor nunca llega a conocer su pasword, desarrollándose todo el proceso de cifrado y descifrado siempre del lado del cliente.
>
> El punto débil de este criptosistema ocurre cuando la web ve comprometida su seguridad y con ella la de su código JS, ya sea por la intervención de un programador deshonesto de la misma organización, ya sea por la intervención de terceros que pueden introducir fragmentos de código malicioso con objeto, por ejemplo, de abrir un socket durante el proceso de cifrado para capturar y enviar la clave del usuario a un determinado sitio.

No se si la propuesta ha avanzado en alguna dirección pero a lo mejor valía la pena probar.
