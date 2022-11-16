--- 
layout: post
title: "Automatización de lo que se ve en el perfil de GitHub"
date: "Thu Aug 06 15:02:01 +0100 2020"
category: desarrollo
tags: [desarrollo, github, API, README, howto]
imagefeature: https://github.com/fernand0/fernand0/blob/master/img/Screenshot%20from%202020-08-06%2019-10-17.png?raw=true
---

<a href="https://github.com/fernand0/fernand0/" title="Centro de Exposiciones del Centro de Conocimiento sobre se… "><img src="https://github.com/fernand0/fernand0/blob/master/img/Screenshot%20from%202020-08-06%2019-10-17.png?raw=true" alt="Imagen de la página " width="240" style="float:left; margin:5px"></a>
Programar me relaja y además me gusta hacer pruebas, aunque el tiempo disponible no sea demasiado. También me gustaría incluir en esta bitácora algunas de esas pruebas, por si le sirven a alguien para algo, que es algo que necesita todavía más tiempo. 
Esta entrada pretende mostrar una de esas pruebas, que permite **actualizar automáticamente el perfil de GitHub** gracias a algunas características que han incluido recientemente en esa 'red social' de desarrolladores.

Lo que cuento se basa en las indicaciones que se pueden encontrar en [Building a self-updating profile README for GitHub](https://simonwillison.net/2020/Jul/10/self-updating-profile-readme/) (sigo el sitio de Simmon Willison desde hace mucho tiempo y fue una sorpresa agradable descubrir la receta y otras inspiraciones) y también en [How I Built A Self-Updating README On My Github Profile](https://www.mokkapps.de/blog/how-i-built-a-self-updating-readme-on-my-git-hub-profile/) (en este caso encontrado gracias a una búsqueda de Google y con algunas ideas de diseños más atractivos, al menos para mi).

[GitHub](https://github.com/) ha lanzado recientemte el léeme del perfil (*README*) que permite utilizar *markdown* para incluir información personalizada en el perfil del usuario. Basta con crear un repositorio público nuevo con el nombre del propio usuario (en mi caso, [github.com/fernand0/fernand0](https://github.com/fernand0/fernand0) e incluir un fichero *README*. 
GitHub utilizará este fichero para mostrarlo en nuestra página de perfil.

Siendo un repositorio, uno puede preguntarse (al menos Willison lo hizo) si puede **automatizar algunas tareas** relacionadas con el mismo.
Y nos cuenta como esto es posible gracias a una acción de GitHub (*GitHub Action*) que se define en el fichero [build.yml](https://github.com/fernand0/fernand0/blob/master/.github/workflows/build.yml). 

No voy a entrar en mucho detalle, pero contiene:

* Formas de **'disparar' acciones** (en nuestro caso, cuando se hace un *push* o basado en el tiempo, con la sintáxis del *crontab*). 
* Después, permite **ejecutarlas** (dónde se ejecuta -sistema y entorno de desarrollo, incluyendo instalación de paquetes si es necesario-: en mi caso en una Ubuntu con el lenguaje Python) y algunas cosas más (por ejemplo, definir *TOKENS* necesarios para realizar determinadas acciones -en nuestro caso, utilizar el *Graph QL* API de GitHub).
* Finalmente, **utilizar el resultado** de esas acciones para generar la información que aparecerá en nuestro perfil (Fundamentalmente hacer un *push* si ha habido cambios).

Sobre mi actividad en el propio sitio, decidí incluir información relacionada con repositorios (contribuciones -mínimas- a los de otros proyectos y a mis propios repositorios públicos). 
Sobre otra actividad, pensé en incluir las últimas entradas en mis dos bitácoras más activas (incluye esta) y se muestran en la página.

El **código de actualización** está en [build_readme.py](https://github.com/fernand0/fernand0/blob/89e087ef772db03624450203d2c8b643ffee986a/build_readme.py) (versión en el momento de escribir esta entrada del código basado en el de Willison, las partes mejor realizadas son mérito suyo, las más feas son mis propios 'apaños').

Para **mostrar la información de los repositorios**, como decía arriba, se utilizan el *Graph QL* API de GitHub con un *token* personal (en '[Settings](https://github.com/settings/profile)'  de la cuenta de GitHub podemos buscar la opción de '[Developer settings](https://github.com/settings/apps)' y  allí crear lo que llaman '[Personal access tokens](https://github.com/settings/tokens)'. Luego hay que darle los permisos adecuados para este *token* (en mi caso los de usuario, los de workflow, y los de lectura y escritura en un repo -así a ojo, creo que son los necesarios; si no funciona ya nos dirá cuáles necesitamos-).

Para que el sistema que ejecuta nuestro programa **tenga acceso** al *token* podemos usar los '[settings](https://github.com/fernand0/fernand0/settings)' del proyecto (estos son los míos, pero se entiende, espero) y allí ir a la opción de '[Secrets](https://github.com/fernand0/fernand0/settings/secrets)' donde podemos dar de alta la información secreta que necesitemos.

En mi caso, la información que se muestra sobre la actividad en GitHub está en la pregunta:

    query MyQuery {
      user(login: "fernand0") {
        repositoriesContributedTo(last: 20, orderBy: {field: PUSHED_AT, direction: DESC}) {
          edges {
            node {
              name
              description
              projectsUrl
              pushedAt
            }
          }
        }
        repositories(last: 10, orderBy: {field: UPDATED_AT, direction: ASC}, privacy: PUBLIC) {
          edges {
            node {
              name
              description
              projectsUrl
              owner {
                login
              }
              pushedAt
            }
          }
        }
      }
    }


Para construirla GitHub nos proporciona una herramienta muy útil, que es el '[GitHub GraphQL API'](https://developer.github.com/v4/explorer/) que simplifica mucho la tarea de probar las preguntas. 

Para **mostrar la información de las bitácoras**, utilizo el paquete 'feedparser' que ya usábamos hace algún tiempo en [Publicar en Facebook las entradas de este sitio usando Python](http://fernand0.github.io/Publicar-En-Facebook-Las-Entradas-De-Este-Sitio/) para extraer la información, formatearla y añadirla al *README*.

Por otro lado, de Hoffman he mirado los simbolitos sociales (y he descubierto [Shields.io](https://shields.io/) que parece un sistema de generación de logos utilizando SVG y otros trucos; he usado algunos que ya tenía Hoffman y he 'añadido' otros que no existían, no se qué sucederá) y el formato en una sola columna (Willison tiene una tabla con tres columnas que no se ven muy bien, por ejemplo, en el navegador de un teléfono móvil).


**¿Qué pasará a partir de ahora?**

Probablemente seguiré jugando con el aspecto para dejar uno que me convenza del todo y, tal vez, añada algún servicio más. Uno evidente es el de Twitter, pero podría ser otra cosa.

Si alguien necesita ayuda con algún paso, puede leer con calma las entradas recomendadas y también preguntar, si lo que necesita no es muy diferente de lo que se puede ver aquí.
