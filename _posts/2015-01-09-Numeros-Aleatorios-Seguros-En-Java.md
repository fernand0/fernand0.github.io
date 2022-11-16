---
layout: post
title: "Números aleatorios seguros en Java"
date: "Fri Jan 09 09:10:01 +0100 2015"
category: seguridad
tags: seguridad java programación prng aleatorio random 
---


<a href="https://www.flickr.com/photos/44124419077@N01/152110645/" title="Bolas en el bombo"><img src="https://farm1.staticflickr.com/49/152110645_43aafcb33c_m.jpg" width="240"  alt="Azar" style="float:left; margin:5px"></a>

El tema de los números aleatorios de calidad para aplicaciones con requerimientos de seguridad no aparece habitualmente más que en los comentarios más técnicos. En [Proper use of Java’s SecureRandom](http://www.cigital.com/justice-league-blog/2009/08/14/proper-use-of-javas-securerandom/) hay un texto donde se comenta el uso del generador de números seudo aleatorios seguro de Java.

>When generating random numbers in Java for cryptographic purposes, many developers often use the java.security.SecureRandom class. And while the java.security.SecureRandom class is designed to generate cryptographically secure random numbers, there are a few subtleties in the API, and if it is used improperly the output can become predictable. At Cigital we have witnessed a number of cases where this is true. The following is a guide to the proper use of Java’s java.security.SecureRandom class.

Los consejos:

> * Always specify the exact PRNG and provider that you wish to use. If you just use the default PRNG, you may end up with different PRNGs on different installations of your application that may need to be called differently in order to work properly. Using the following code to get a PRNG instance is appropriate: SecureRandom sr = SecureRandom.getInstance("SHA1PRNG", "SUN");
> * When using the SHA1PRNG, always call java.security.SecureRandom.nextBytes(byte[]) immediately after creating a new instance of the PRNG. This will force the PRNG to seed itself securely. If for testing purposes, you need predictable output, ignoring this rule and seeding the PRNG with hard-coded/predictable values may be appropriate.  
> * Use at least JRE 1.4.1 on Windows and at least JRE 1.4.2 on Solaris and Linux. Earlier versions do not seed the SHA1PRNG securely.  
> * Periodically reseed your PRNG as observing a large amount of PRNG output generated using one seed may allow the attacker to determine the seed and thus predict all future outputs.

Esto es, especificar el generador que se va a utilizar explícitamente (para evitar terminar utilizando diferentes generadores en diferentes configuraciones e instalaciones); cuidado con que la incialización se haga de manera correcta (e imprendecible); las versiones recomendadas eran en aquel momento JRE 1.4.1 para Windows y JRE 1.4.2 para Solaris y Linux por lo menos; reinicializar la semilla del PRNG para reducir la utilidad de la información generada.  

El otro día hablábamos del [Generador de números aleatorios de Intel](http://fernand0.github.io/Generador-Numeros-Aleatorios-Intel/) y allí se pueden encontrar un par de enlaces más sobre el tema.
