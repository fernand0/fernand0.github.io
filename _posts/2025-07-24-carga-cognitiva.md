---
layout: post
title: "Complejidades y carga cognitiva"
date: "2025-07-24 15:00:00 +0000"
category: desarrollo
tags:
- desarrollo
- programación
- complejidad
imagefeature: "https://live.staticflickr.com/65535/51748003787_63bd7c82bc_z.jpg"
---
<a data-flickr-embed="true" href="https://www.flickr.com/photos/fernand0/51748003787/in/dateposted/" title="Mecanismo"><img src="https://live.staticflickr.com/65535/51748003787_63bd7c82bc_z.jpg" width="640" height="427" alt="Mecanismo"/></a><script async src="//embedr.flickr.com/assets/client-code.js" charset="utf-8"></script>

En [Cognitive load is what matters](https://minds.md/zakirullin/cognitive) se hablar de la carga cognitiva del desarrollo, que tiene que ver con lo que la persona que desarrolla tiene que pensar para completar su tarea.

> Cognitive load is how much a developer needs to think in order to complete a task.

Cuando desarrollamos programas (*software*) podemos acudir a muy diversos niveles de abstracción. Manejamos infomación como valores, control del flujo y secuencias de llamadas, pero nuestra cabeza puede manejar esto hasta un cierto nivel.

> When reading code, you put things like values of variables, control flow logic and call sequences into your head. The average person can hold roughly four such chunks in working memory. Once the cognitive load reaches this threshold, it becomes much harder to understand things.

Hay dos tipos de carga, la intrínseca, provocada por la dificultad de la tarea.

> Intrinsic - caused by the inherent difficulty of a task. It can't be reduced, it's at the very heart of software development.

Y extrínseca, que tiene que ver con la forma en que se presenta la información, y que es sobre la que podríamos intervenir.

> Extraneous - created by the way the information is presented. Caused by factors not directly relevant to the task, such as smart author's quirks. Can be greatly reduced. We will focus on this type of cognitive load.

Por ejemplo, podríamos reducir expresiones lógicas complejas mediante la adición de variables que simplifiquen el proceso y nos den pistas. Copio sus ejemplos:

Complicado:

    if val > someConstant // 🧠+
    && (condition2 || condition3) // 🧠+++, prev cond should be true, one of c2 or c3 has be true
    && (condition4 && !condition5) { // 🤯, we are messed up by this point
    ...
    }

Más sencillo:

    isValid = val > someConstant
    isAllowed = condition2 || condition3
    isSecure = condition4 && !condition5
    // 🧠, we don't need to remember the conditions, there are descriptive variables
    if isValid && isAllowed && isSecure {
        ...
    }

Y se puede simplificar de más formas, pero creo que se ve la idea.

También nombra las salidas prematuras (*early returns*) que tanto les gustan a las inteligencias artificiales (o, al menos, eso es lo que he visto).

También puede haber otros tipos de complejidad relacionados con algunas construcciones que son ventajosas, como la herencia (que si se nos va de las manos puede obligarnos a llevar en la cabeza varios lugares del código donde pasan cosas interesantes.

>  Inheritance nightmare

¿Y qué sucede cuando tenemos demasiados métodos pequeños, clases y módulos?
Demasidado de cualquier cosa (por mucho que los consejos nos recomienden tener métodos pequeños, compartimentalización, ...) es un problema en sí mismo.

> Having too many shallow modules can make it difficult to understand the project. Not only do we have to keep in mind each module responsibilities, but also all their interactions. To understand the purpose of a shallow module, we first need to look at the functionality of all the related modules. 🤯

Habla de otros casos relacionados como la exitencia de muchos microservicios en contraposición con un 'monolito' bien diseñado.

> A well-crafted monolith with truly isolated modules is often much more flexible than a bunch of microservices. It also requires far less cognitive effort to maintain.

Otro caso interesante es el de los lenguajes con muchas características: lo que a priori parece una buena idea, resulta en un problema a la hora de aprender cosas nuevas, decidir cuáles usar, cómo, dónde...

> You not only have to understand this complicated program, you have to understand why a programmer decided this was the way to approach a problem from the features that are available. 🤯

Un buen ejemplo es el de los códigos de respuesta del protocolo HTTP: por un lado son amplios y flexibles, pero al final vuelve a ocurrir lo mismo. Los desarrolladores usan menos porque es más sencillo para ellos, y los consumidores no son capaces de diferenciar los pequeños detalles que los diferencian, cuando probablemente sería mucho mejor devolver otro tipo de información.

> Why hold this custom mapping in our working memory? It's better to abstract away your business details from the HTTP transfer protocol, and return self-descriptive codes directly in the response body

Termina hablando de las arquitecturas con nivels (*Layered architecture*), donde la abstracción que nos ayuda a ocultar la complejidad añade indirecciones (y dificultades cuando estamos buscando problemas).

> Abstraction is supposed to hide complexity, here it just adds indirection. Jumping from call to call to read along and figure out what goes wrong and what is missing is a vital requirement to quickly solve a problem.

El compromiso que suponen las ventajas frente a las difultades, que solo puede resolver la experiencia y el conocimiento.

> So, why pay the price of high cognitive load for such a layered architecture, if it doesn't pay off in the future?

He hecho un resumen, pero creo que es un buen resumen-recordatorio de cuestiones que deberíamos tener claras a la hora de abordar proyectos.
Salvo que esos proyectos sean, precisamente, para aprender estas cosas.




