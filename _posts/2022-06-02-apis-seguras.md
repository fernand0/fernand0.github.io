---
layout: post
title: "Algunos consejos sobre la seguridad en APIs"
date: "2022-06-02 15:00:00 +0000"
category: seguridad
tags:
- seguridad
- API
- programación
- desarrollo
imagefeature: 'https://live.staticflickr.com/65535/51059742416_961843b5a9.jpg'
---
<a href="https://flickr.com/photos/fernand0/51059742416/" title="Puerta "><img src="https://live.staticflickr.com/65535/51059742416_961843b5a9.jpg" alt="Puerta " class="img-responsive img-centered"></a>
Le vamos dedicando más atención a las APIs (esos sistemas que nos permiten ofrecer la funcionalidad de nuestro sitio a otros -o a nuestros propios desarrolladores- más allá de la que sea nuestra aplicación principal -si es que eso existe-).

En [Secure APIs in ASP.NET](https://omegapoint.se/secure-apis-in-aspnet) una serie de recomendaciones para este lenguaje (poco nombrado, aunque con su cuota de uso) pero, como casi siempre, con uso en muchos otros casos.

Las recomendaciones:

Validar que la petición es correcta, esto es: formato adecuado, tamaño adecuado, contenido adecuado...

> The first step in the model is to validate that the incoming request is valid HTTP, with the correct format and a reasonable size. Otherwise, it should be rejected as early as possible before reaching our application code.

Validar los *tokens*, que sería una forma de validar las peticiones, pero refiriéndose a la parte de identificación, autentificación, autorización... Siempre, con el modelo de aceptar lo que es correcto, esto es: hacer obligatoria la autorización.

> An essential part of step 2 is that we make authorization mandatory. The policy lines in the code above ensure that the default behavior requires an authenticated request. Security should never be opt-in. Instead, you opt out when needed. 

Transformar los *tokens* de acceso en permisos: a una autentificación correcta, y ante cualquier intento de realizar acciones hay que estar seguros de que esa autorización permite realizar la acción solicitada.

> Before moving to step 4, we want to emphasize the importance of striking the right balance between what the token contains and the permissions we need for access control.


Validar los datos de la petición: los parámetros son los que tienen que ser, de los tipos adecuados, ... Así evitaremos que a través de los parámetros puedan entrar inyecciones peligrosas de datos.

> For the endpoint in our controller, we have one parameter: the product identifier. In our case, the identifier is not an arbitrary string of any size! It can contain only letters and digits and be ten characters or less. If the input string does not follow those rules, we can immediately return a 400 Bad Request. This input validation will make injection attacks a lot harder.

Validar los permisos para realizar la operación. Si una petición no viene con la solicitud adecuada de permisos (de acuerdo a nuestro sistema interno, claro), no permitiremos la acción.

> We base the permission to perform an operation on the transformed permissions in our domain code and not directly with scopes and user identity.

Finalmente, validar los permisos para acceder a los datos: una vez que los permisos son correctos, están adecuadamente incluidos, tenemos que validar en nuestra aplicación que esos datos se pueden proporcionar de acuerdo a la política que tengamos definida.

> The final step is to validate access to the actual data that the request will read or modify. Sometimes we can validate access by looking at the request, and other times we need to retrieve the data before deciding.

Viene con ejemplos en el lenguaje y más comentarios interesantes. 


