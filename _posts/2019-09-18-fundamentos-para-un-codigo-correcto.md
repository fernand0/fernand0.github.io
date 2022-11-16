--- 
layout: post
title: "Algunas ideas sobre código correcto"
date: "Wed Sep 18 16:05:01 +0100 2019"
category: desarrollo
tags: [desarrollo, programación, correcto, contrato, defensiva]
imagefeature: https://live.staticflickr.com/4115/4934690400_7359ac5382_m.jpg
---

<a href="https://www.flickr.com/photos/fernand0/4934690400" title="Un contrato..."><img src="https://live.staticflickr.com/4115/4934690400_7359ac5382_m.jpg" width="240"  alt="Un contrato..." style="float:left; margin:5px"></a>
Otra lectura interesante, [Foundations of Correct Code](https://codemanship.wordpress.com/2019/05/19/foundations-of-correct-code/) donde se habla de que el código no sólo ha de pasar los tests y las pruebas, sino que estas deben tener en cuenta que el código sea correcto.

En este sentido nos recuerda los conceptos de los contratos, pre y post-condiciones y nos recuerda su historia:

> You may well have heard the terms before: contract, pre-condition, post-condition. But you might not be aware of their origins.

Posteriormente, entra en la discusión entre lo que llamamos programación defensiva (si no se cumple lo que esperamos lanzamos un error antes de hacer algo que, a priori, puede ser incorrecto) o bien el diseño por contrato, basado en el principio de que si el proveedor cumple su parte, nosotros devolveremos un resultado correcto.

> We have two choices here: defensive programming, and Design by Contract.

...

> Defensive programming guards the body of a function or method, checking that the pre-condition holds and throwing an error if it doesn’t.

...

>  all of the interactions between its components must be correct. A Hoare triple describes a contract between a client and a supplier of a service (e.g., a method of a class), such that the supplier ensures that the post-condition is satisfied, and the client ensures that they never a method or function unless the pre-condition is satisfied.

A la hora de elegir, puede depende de nuestra relación con el resto de proveedores: si nosotros producimos todo el código, hay cosas que podemos (o deberíamos poder) asegurar. En otros casos, tenemos que tener cuidado con lo que hayan podido hacer otras personas.

> One final thought on defensive programming vs. Design by Contract, relating to the design of the system as a whole: when it’s us writing the client code, we have control over whether the inputs are correct. When someone else is providing the inputs – e.g., a web service client, or an end user – we don’t have that control. So it’s usually necessary to code defensively at system/service boundaries.

Tampoco tiene sentido conformarse con lanzar un error cuando algo no vaya bien: normalmente el usuario puede que ni siquiera tenga la culpa y nosotros tampoco queremos molestarle.

> Offering users choices that aren’t actually available and then displaying an error message when they select them not only annoys the user, but also complicates the application’s internal logic as it now has to handle more edge cases.

De esta forma, es posible que tengamos que usar ambas aproximaciones:

> I’ve found the best approach to delivering correct software that’s simple in its internal logic is to design the UX carefully to simplify the inputs, do some defensive programming just below the UI to validate the inputs, and then apply Design by Contract for all the internal logic, with test-time assertion checking in case we made a boo-boo in some client code.
