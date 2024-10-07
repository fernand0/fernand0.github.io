---
layout: post
title: "Entrada a los programas, visibilidad y posibilidades de espiar"
date: "2024-10-07 15:00:00 +0000"
category: seguridad
tags:
- programación
- desarrollo
- visibilidad
- parámetros
- argumentos
imagefeature: "https://live.staticflickr.com/254/522122174_0849cd409b_z.jpg"
---

<a data-flickr-embed="true" href="https://www.flickr.com/photos/fernand0/522122174/in/photolist-N91Js-e3e5Jj" title="Cambio de gafas. Antes y después."><img src="https://live.staticflickr.com/254/522122174_0849cd409b_z.jpg" width="640" height="480" alt="Cambio de gafas. Antes y después."/></a><script async src="//embedr.flickr.com/assets/client-code.js" charset="utf-8"></script>

En [Why you should use STDIN to read your program arguments](https://victoronsoftware.com/posts/get-args-from-stdin/) nos recordaban hace unas semanas que la lectura de parámetros para un programa es más segura si se hace desde la entrada estándar que desde variables de entorno o parámetros de la línea de órdenes.

> STDIN is more secure than environment variables or command-line arguments

Algunas razones son que los parámetros de la línea de órdenes son visibles cuando se ejecuta la instrucción `ps`, lo que significa que cualquier usuario local podría verlos y, por lo tanto, obtener información útil.

> When you pass command-line arguments to a program, they are visible to anyone who can run the ps command. Allowing others to read arguments is a security risk if the arguments contain sensitive information like passwords or API keys.

Por otra parte, cuando hablamos de las variables de entorno también son accesibles para alguien que pueda ejecutar `ps` (`ps eww <PID>`), y además son visibles para el programa y, por lo tanto, cualquier parte de nuestra aplicación podría tener acceso a ellas.

> Environment variables are also visible to anyone who can run the ps command. They are also globally visible to the program, so any arbitrary code in your application can extract the environment variables.

Sin embargo, si usamos STDIN, lo que hay allí no es visible para `ps`, y tampoco es visible de manera global para todo el programa.

> STDIN is more secure because it is not visible to the ps command and is not globally visible to the program. Thus, only the parts of the program that explicitly read from STDIN can access this data.

Luego da algún ejemplo sobre la forma de hacerlo en Go, y cómo integrarlo con otros mecanismos para guardar información.

