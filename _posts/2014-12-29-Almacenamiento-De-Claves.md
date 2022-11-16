---
layout: post
title: "Consejos para almacenar las claves"
date: "Wed Dec 29 20:55:01 +0100 2014"
category: seguridad
tags: seguridad claves contraseñas almacenamiento   
---

En [Do any security experts recommend bcrypt for password storage?](http://security.stackexchange.com/questions/4781/do-any-security-experts-recommend-bcrypt-for-password-storage) y, en particular, en la primera respuesta un buen texto sobre el almacenamiento de claves y los algoritmos adecuados para hacerlo. Se discute sobre [Bcrypt](http://en.wikipedia.org/wiki/Bcrypt) y [PBKDF2](http://en.wikipedia.org/wiki/PBKDF2) y se comenta sobre alguno más.

Para este tipo de almacenamiento hoy en día hay que tener en cuenta ataques bastante esotéricos con [GPU](http://en.wikipedia.org/wiki/Graphics_processing_unit) (procesadores gráficos) y [FPGA](http://en.wikipedia.org/wiki/Field-programmable_gate_array) como herramientas de cálculo masivo de manera muy eficiente. Los nuevos algoritmos tienen que tener en cuenta no sólo la velocidad de cálculo, sino también la cantidad de RAM utilizada y otros parámetros.

Se puede completar la lectura con [The Theory](http://security.stackexchange.com/questions/211/how-to-securely-hash-passwords/31846#31846) que es un enlace directo a la primera respuesta de otra pregunta sobre el tema, con un análisis de las necesidades actuales, ventajas en inconvenientes de las principales soluciones... 

La conclusión, en este caso es:

>Use bcrypt. PBKDF2 is not bad either. If you use scrypt you will be a "slightly early adopter" with the risks that are implied by this expression; but it would be a good move for scientific progress ("crash dummy" is a very honourable profession)

Que es bastante parecida a la del artículo anterior.
