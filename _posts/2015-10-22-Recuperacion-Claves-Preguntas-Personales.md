---
layout: post
title: "Recuperación de contraseñas con preguntas personales"
date: "Thu Oct 22 19:55:01 +0100 2015"
category: seguridad
tags:  [seguridad, contraseñas, claves, passwords, credenciales, recuperación, preguntas]
---





<a href="https://500px.com/photo/110270333/usted-me-confunde-by-fernando-tricas" title="Credenciales"><img src="https://drscdn.500px.org/photo/110270333/h%3D300/3f9db7756125038722cd5c83954235b6" width="240"  alt="Intento de robo de credenciales" style="float:left; margin:5px"></a>

Tengo que reconocer que me encanta el tema de las contraseñas, gestión, almacenamiento, recuperación... También que se leen muchas cosas por ahí y que no siempre están respaldadas por información actualizada y obtenida por medios más o menos rigurosos.
Por eso me he leído rápidamente un artículo de Joseph Bonneau, Elie Bursztein, Ilan Caron, Rob Jackson y Mike Williamson, [Secrets, Lies, and Account Recovery: Lessons from the Use of Personal Knowledge Questions at Google](http://research.google.com/pubs/pub43783.html) donde se habla de algunos datos obtenidos en Google sobre la validez y gestión de los sistemas de recuperación de cuentas basados en preguntas secretas.
Recordemos que el 'folklore' suele decir que una pregunta secreta sólo es una contraseña más débil.

Su análisis parece confirmar que la pregunta de seguridad rebaja el nivel de seguridad y esto sucede, curiosamente, porque los usuarios no son sinceros y tratan de inventarse las respuestas para hacerlas más seguras (lo que, en agregado, hace que sean peores). También muestran que es casi imposible conseguir preguntas cuyas respuestas sean fáciles de recordar y que a la vez sean seguras.

> Abstract: We examine the first large real-world data set on personal knowledge question's security and memorability from their deployment at Google. Our analysis confirms that secret questions generally offer a security level that is far lower than user-chosen passwords. It turns out to be even lower than proxies such as the real distribution of surnames in the population would indicate. Surprisingly, we found that a significant cause of this insecurity is that users often don't answer truthfully. A user survey we conducted revealed that a significant fraction of users (37%) who admitted to providing fake answers did so in an attempt to make them "harder to guess" although on aggregate this behavior had the opposite effect as people "harden" their answers in a predictable way. On the usability side, we show that secret answers have surprisingly poor memorability despite the assumption that reliability motivates their continued deployment. From millions of account recovery attempts we observed a significant fraction of users (e.g 40\% of our English-speaking US users) were unable to recall their answers when needed. This is lower than the success rate of alternative recovery mechanisms such as SMS reset codes (over 80%). Comparing question strength and memorability reveals that the questions that are potentially the most secure (e.g what is your first phone number) are also the ones with the worst memorability. We conclude that it appears next to impossible to find secret questions that are both secure and memorable. Secret questions continue have some use when combined with other signals, but they should not be used alone and best practice should favor more reliable alternatives. 

Hay muchos más hallazgos y vale la pena leer el artículo; por ejemplo, algo que no nos soprenderá: la respuesta a las preguntas secretas es peor conforme pasa el tiempo porque no la recordaremos.

Hace algún tiempo comentábamos en [Las claves](https://mbpfernand0.wordpress.com/2011/07/21/las-claves/) sobre los sistemas de recuperación y el entrevistado los defendía, si se seleccionaban adecuadamente las preguntas secretas. Por cierto, en la [Forgot Password Cheat Sheet](https://www.owasp.org/index.php/Forgot_Password_Cheat_Sheet) sigue incluyendo la parte de las preguntas aunque habla más bien de asegurarse de la identidad, lo que significa que el enfoque también ha cambiado un poco.

¿La apuesta de Google hoy en día? 
Recuperación a través del móvil (SMS) y el correo.

Aunque los malos ya se lo han aprendido ([Si Google te envía un SMS para decirte que alguien ha accedido a tu cuenta… ¡Cuidado!](http://www.pandasecurity.com/spain/mediacenter/noticias/google-sms/) y seguramente veamos dentro de poco  más ataques sobre estos sistemas (sin olvidar que son muy poco fuera de banda, al estar muchas veces en el mismo dispositivo que las apps que intentan autentificarse).
