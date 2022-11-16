--- 
layout: post
title: "Las restricciones sobre contraseñas generan contraseñas peores"
date: "Tue Feb 12 15:05:01 +0100 2019"
category: seguridad
tags: [seguridad, contraseñas, claves, restricciones, fuerza, bruta]
imagefeature: https://avecesunafoto.files.wordpress.com/2018/11/img_20180816_113821.jpg
---


<a href="https://avecesunafoto.wordpress.com/2018/11/05/calculadora-2/" title="Teclas"><img src="https://avecesunafoto.files.wordpress.com/2018/11/img_20180816_113821.jpg" width="240"  alt="Teclas" style="float:left; margin:5px"></a>
Algunos administradores que pueden hacerlo (seguramente, los mismos que pueden obligarnos a cambiar de contraseña, como contábamos en [Los cambios frecuentes de contraseña son contraproducentes](http://fernand0.github.io/Cambios-Contrase%C3%B1a-Frecuentes/) creen que añadir una restricción a nuestra contraseña indicando que contenga una cifra y un caracter especial (o variaciones similares) mejora las contraseñas.
Lo cierto es que, si permitimos estos caracteres en las claves puede que mejoren (siempre que no se hagan substituciones obvias: l por 1, e por 3, ...). Pero siobligamos a que estén, le estamos dando pistas a los 'malos': pueden hacer búsquedas en el espacio de claves, poniendo menos alternativas en algunas posiciones (el caso más delirante, que he visto en un par de sitios es 'forzar' a que esos caracteres estén en determinadas posiciones). 
Sin olvidarnos de que cuando eso contraviene nuestras propias costumbres en la generación de contraseñas, tenemos la receta segura para que no la recordemos, o la hagamos peor para estar seguros de recordarla.

De eso hablaban en [How Password Constraints Give You a False Sense of Security](https://lifehacker.com/how-password-constraints-give-you-a-false-sense-of-secu-1830564360) y yo lo traigo aquí para animar a tantos y tantos administradores a no ser creativos en estas cosas.

Hace un poco de numerología con lo que ahorraría un hipotético atacante sabiendo que tiene que haber, digamos, un dígito:

> Assume they can test about 31 billion passwords per second. Cracking their way through your reasonably complicated eight-character password could take, at most, 212,903 seconds. That’s 3,548 minutes, or roughly two and a half days.
>
> Now, let’s talk about constraints for a minute. Assume that the service you’re using requires you to have an eight-character password. Abrams notes that takes 70.6 trillion passwords out of the mix, since every password from a single character long to seven character long is now invalid. That saves the cracking tool a whopping 2,277 seconds, or nearly 38 minutes. That’s not too bad.

Vale la pena leer el resto de argumentos numéricos pero, al final, la conclusión es que lo mejor es que la contraseña sea más larga, incluso en sistemas con restricciones.

> Instead of worrying about the best way to make your shorter password harder to guess or brute-force, Abrams advises that it’s a lot better to pick a longer password, because even if a service has password constraints, they’ll have much less of an impact: [...]
