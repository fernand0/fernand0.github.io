---
layout: post
title: "Registrando IPs de nuestros dispositivos en una hoja de cálculo en la nube"
date: "Tue Apr 13 21:20:01 +0100 2017"
category: programación
tags: [programación, python, ip, red, dispositivos, google, spreadsheets]
imagefeature: https://c2.staticflickr.com/8/7053/8687705871_eee51f4113_m.jpg
---




<a href="https://www.flickr.com/photos/fernand0/8687705871" title="Dirección"><img src="https://c2.staticflickr.com/8/7053/8687705871_eee51f4113_m.jpg" width="240"  alt="Dirección" style="float:left; margin:5px"></a>
Seguimos dándole vueltas al tema de la dirección IP de los dispositivos. En [¿Quién está en mi red?](https://mbpfernand0.wordpress.com/2014/07/16/quien-esta-en-mi-red/) abordábamos el problema desde el punto de vista del escaneo de la red.

Otra posibilidad es, claro, mirar el router y mirar los dispositivos conectados.

Sin embargo, para los dispositivos que tenemos controlados (y que nos interesan más) una posibilidad puede ser establecer un registro: cuando se conectan informan de que se han conectado, su IP, y los datos que consideremos relevantes. 

Seguro que hay alguna forma canónica de hacer esto (o no, porque igual lo suyo sería tener un router que nos proporcione esta información de manera conveniente -pista: que no haga falta un navegador-) pero me pareció un buen ejercicio. 
Descubrí [Google Spreadsheets and Python](https://www.twilio.com/blog/2017/02/an-easy-way-to-read-and-write-to-a-google-spreadsheet-in-python.html) y me pareció una buena forma de intentarlo: los dispositivos podrían registrar en una hoja de cálculo los datos que nos interesen.
Para la instalación y configuración básica se puede seguir ese documento. Después, tenemos que hacer un programita que recabe los datos y los almacene. El mío se basa en el ejemplo que puede verse allí.

En nuestro caso, obtendremos la IP con:

{% highlight python %}
def getIp():
    return([l for l in ([ip for ip in socket.gethostbyname_ex(socket.gethostname())[2] if not ip.startswith("127.")][:1], [[(s.connect(('8.8.8.8', 53)), s.getsockname()[0], s.close()) for s in [socket.socket(socket.AF_INET, socket.SOCK_DGRAM)]][0][1]]) if l][0][0])
{% endhighlight %}

En este caso seguimos lo que indicaban en [Finding local IP addresses using Python's stdlib](http://stackoverflow.com/questions/166506/finding-local-ip-addresses-using-pythons-stdlib), no comentaremos más.

Además guardamos el nombre de la máquina, que nos servirá para dar nombre a la pestaña de la hoja donde almacenaremos los datos:

{% highlight python %}
    hostname = socket.gethostname()
{% endhighlight %}

Finalmente, ya sólo nos queda escribir en la hoja de cálculo:


{% highlight python %}
    sheet_name = 'Registro IPs'
{% endhighlight %}

A continuación accedemos a la hoja de cálculo (cuidado con la gestión de credenciales, nosotros hemos almacenado en la variable client_secret el nombre del fichero donde están los datos necesarios:

{% highlight python %}
    scope = ['https://spreadsheets.google.com/feeds']
    creds = ServiceAccountCredentials.from_json_keyfile_name(client_secret, scope)
    client = gspread.authorize(creds)
    
    sheet = client.open(sheet_name)
{% endhighlight %}

A continuación registramos la máquina. Si ya es una máquina conocida, simplemente accedemos a la pestaña correspondiente; si no, la creamos:


{% highlight python %}
    try:
        worksheet = sheet.worksheet(hostname)
    except gspread.exceptions.WorksheetNotFound:
        worksheet = sheet.add_worksheet(hostname, 5, 5)
{% endhighlight %}
 
Finalmente, escribimos en la hoja, insertando una fila antes de la segunda (la idea es que la información más reciente estará arriba, más cerca para verla). Al añadir una fila tendremos un registro de conexiones.

El código (en su versión actual) se puede ver en [scripts/registerIp.py](https://github.com/fernand0/scripts/blob/ad683a3fc6fee2618f1ce32487b5148d142404c2/registerIp.py).

En

<iframe width="560" height="315" src="https://www.youtube.com/embed/aFz5I_52b1o" frameborder="0" allowfullscreen></iframe>

podemos ver cómo se crea la pestaña y se rellenan los datos al invocar el programa.

Para mantener este registro podemos poner en /etc/rc.local una invocación al programa de manera que cuando se arranquen los distintos sistemas registren su presencia.
