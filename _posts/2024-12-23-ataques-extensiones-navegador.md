---
layout: post
title: "Las extensiones de los navegadores y algunos consejos sobre su seguridad"
date: "2024-12-23 15:00:00 +0000"
category: seguridad
tags:
- seguridad
- navevador
- extensione
- browser
imagefeature: "https://live.staticflickr.com/7536/16060304391_89d704d0d5_z.jpg"
---
<a data-flickr-embed="true" href="https://www.flickr.com/photos/fernand0/16060304391/in/photolist-3aMqRZ-3aMrjg-3aRWbY-3aRWDd-qtcfXR-4mvBWH-4mDxfN-4pDyX3-4NLFUp-4NQWi3-5BLMZs-5BLMZw-5BLMZC-5K9c9r-61YvNu-6oeuVL-6oYzct-7Fsx3v-8E3Ca2-bycZLT-dmzf68-e1vvox-e1vvpa-e1vvqZ-eFiUxU-7Tms-dhWDK-3aMqut-3aRVM1-e17h5-2D1jt-2LJWf-2LK55-2LLHj-mD5r8-mD5vL-36ZNB-36ZTF-p8ruD-p8rxf-3sqY9-fHAP-ychGU-kd9x-4QWs5-sQ6J-QrrkT-V81HT-9gmES" title="Libro. There is a cat con the internet!"><img src="https://live.staticflickr.com/7536/16060304391_89d704d0d5_z.jpg" width="640" height="640" alt="Libro. There is a cat con the internet!"/></a><script async src="//embedr.flickr.com/assets/client-code.js" charset="utf-8"></script>

En [Attacking browser extensions](https://github.blog/security/vulnerability-research/attacking-browser-extensions/) un nuevo recordatorio de que las extensiones del navegador son programas externos que ejecutamos en nuestra máquina y que deberíamos prestarles atención.

Una extensión del navegador es un conjunto de ficheros HTML, CSS, y JavaScript que realizan conjuntamente algún tipo de transformación para 'mejorar' nuestra navegación.

> A browser extension is a group of HTML, CSS, and JavaScript files that work together to enhance the browsing experience.

También tienen un fichero de configuración `manifest.json` donde se pueden especificar algunas cuestiones como el contexto de ejecución (contenido, ventanas emergentes -*popup*-, y de fondo).

> In the manifest.json file, we can specify the context that a file will run. The three major contexts are the webpage/content script, the popup and the background.

El contexto de fondo es el más potente, porque permite el acceso a la mayoría de APIs de extensiones del navegador, dándole control sobre la experiencia de navegación, con muchas capacidades.

> The Extension APIs give an extension a lot of control of the user’s browsing experience, with the ability to arbitrarily control tabs, read from the websites, or modify and read cookies, to name a few.

También hay un sistema de permisos, que permite limitar este control.

> Luckily, these abilities are each locked behind permissions, requested in the manifest.json file under the “permissions” key.

Habría que fijarse en permisos como el de pestaña activa (*activeTab*), que puede ser bastante peligroso.

> This activeTab is interesting for exploitation and malicious extensions alike due to its immense power.

Por su parte. los permisos relacionados con el contenido pueden afectar porque interactúan con el *DOM* (modelo de objetos de la página), escuchar las interacciones del usuario, y reaccionar ante ellas.

> The frontend of an extension is just as important as the backend when extensions want to interact with the DOM of the pages visited by the user

...

> The content script may also listen for user interaction on the current page, allowing an action to be taken based on the user interaction.

Finalmente el contexto de las ventanas emergentes tiene que ver con la ejecución de JavaScript que interactuará con la extensión, permitiendo cambios en la configuración, realización de peticiones...

> ... the popup will let the user directly interact with the functionality of the extension, usually allowing them to change settings and make requests to backend servers that are tied to the extension.

Naturalmente, con acceso a las APIs de extensiones, con las correspondientes consecuencias.

> Like the background script, the JavaScript running in the popup page can use all the Extensions APIs that the extension has permissions for and any JavaScript runs in the domain of the extension.

Por lo tanto, las extensiones pueden ser la causa de:

1. Aceptar contenido proporcionado por un atacante y utilizarlo de forma insegura.

> The extension takes attacker-supplied input from the website and uses it in some unsafe way.

2. Otra extensión o un sitio web envían un mensaje a la extensión y ésta la utiliza de forma peligrosa.

> Another extension or a website sends a message to the extension and the extension uses that input in a dangerous way.

3. La extensión utiliza algunos de los parámetros de la URL cuando se carga y los utilizar para realizar alguna operación con privilegio para realizar acciones peligrosas. Para que esto sea posible debería haber algún problema en la configuración.

> The extension takes in URL parameters when it is loaded, and those parameters are used to do a privileged operation. This requires a vulnerable configuration.

La primera consecuencia es que pueden ocurrir cosas malas pero que, en general,  no es tan fácil.

> why browser extensions are generally pretty secure, because it often requires multiple points of failure in order to introduce an exploitable vulnerability

Sobre las posibles vulnerabilidades que podrían ocurrir son las esperables: *cross-site scripting*, *server-side request forgery* e inyección en el API de extensiones (*Extension API injection*).

Entre las mitigaciones, los navegadores implementan aleatorización de los identificadores (*UUID randomization*)  de forma que un ataque en el HTML tenga menos posibilidades de éxito.

> Firstly, many browsers have randomized the ID of the extension, so that attacking exposed HTML files is no longer a threat, unless a leak of the internal ID, called the UUID, can be found.

Modelado con herramientas como CodeQL (proporcionado por GitHub, de cuyo blog es el artículo), que permiten detectar comportamientos maliciosos de algunos flujos de ejecución.

> CodeQL’s code injection query gets a RemoteFlowSource (any Javascript APIs that potentially take in data from an external system or user) and looks for flow into Javascript code injection sinks such as eval.

Interesante. Los 'malos' sólo tienen que encontrar una de todas las vías de entrada que existen.
