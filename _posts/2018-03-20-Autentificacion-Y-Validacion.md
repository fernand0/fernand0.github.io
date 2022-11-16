---
layout: post
title: "Autentificación, validación e identificación de los usuarios. Cada vez un poco más allá."
date: "Tue Mar 20 19:18:01 +0100 2018"
category: seguridad
tags: [seguridad, autentificación, identificación, comportamiento, perfilado]
imagefeature: https://c1.staticflickr.com/3/2215/1535752807_4181367fa9_m.jpg
---


<a href="https://www.flickr.com/photos/fernand0/1535752807" title="Huella"><img src="https://c1.staticflickr.com/3/2215/1535752807_4181367fa9_m.jpg" width="240"  alt="Huella" style="float:left; margin:5px"></a>
Se habla con mucha frecuencia de la autentificación, y de los diversos sistemas disponibles, pero no hay que olvidar que si queremos estar seguros no podemos confiar sólo en ellos. Cada vez más tenemos que utilizar la información adicional de la que dispongamos para estar seguros de que el usuario es quién dice ser.o

En [Trust, but Verify: Authentication Without Validation Is Naïve](https://securityintelligence.com/trust-but-verify-authentication-without-validation-is-naive/) daban algunas ideas sobre ello.

Primero, alguna paradoja: es más probable que las preguntas de seguridad las responda adecuadamente un atacante que el legítimo propietario de la cuenta: 

>  Gartner research, however, found that users fail to answer their knowledge-based questions 15–30 percent of the time, while fraudsters answer correctly 60 percent of the time. Malicious actors often find this information on social networks or through phishing schemes.

Si confiamos en dispositivos como los teléfonos para la validación también nos podemos encontrar problemas:

> his practice has shifted to mobile phones, with OTPs being sent as text messages. However, mobile malware can intercept these messages and forward them to fraudsters.

Y, desde luego, la biometría también tiene sus problemas:

> ...  which has led to the exponential growth of fingerprint reader-enabled devices. It didn’t take long, however, for cybercriminals to circumvent this technology

¿Entonces?
Como decíamos, hay que ser capaces de utilizar la información extra de la que dispongamos. Por ejemplo, sobre el comportamiento, y otros identificadores. 


