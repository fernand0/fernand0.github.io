---
layout: post
title: "Insertar fórmulas de libreoffice en un CSV"
date: "Fri Jul 03 12:45:01 +0100 2015"
category: desarrollo
tags:  desarrollo cálculo libreoffice csv shell script
---





<a href="https://www.flickr.com/photos/fernand0/5230202704/" title="Calculadora"><img src="https://farm6.staticflickr.com/5243/5230202704_8950105d58_m.jpg" width="240"  alt="Calculadora" style="float:left; margin:5px"></a>

Supongamos que tenemos un montón de ficheros de texto que contienen datos que queremos procesar de una determinada manera con nuestra hoja de cálculo. 
El proceso de extracción de la información se puede hacer con más o menos facilidad utilizando un script sencillito (con sus grep, awk, ...) y generamos algo que parece que tiene filas y columnas con datos. 

Si los datos forman agrupaciones sobre las que querríamos hacer ciertos cálculos (por ejemplo, la media de un valor cada cierto número de filas) podríamos trabajar con el propio script, pero a veces necesitamos 'masajear' los datos para ver qué sucede. 

Por eso estuve el otro día viendo cómo se podría hacer y lo comparto aquí. Primero, libreoffice permite insertar fórmulas en un CSV (comma separated values) siempre que la fórmula vaya entre comillas y al insertarla desde un fichero (importarla) no tengamos marcada la opción ('[Quoted field as text](https://help.libreoffice.org/Common/Text_Import#Quoted_fields_as_text)').

Y luego insertamos la fórmula correspondiente en los lugares que nos parezca oportuno. Por ejemplo:

{% highlight bash %}
# Sum of the last 10 rows
sum='"=SUM(INDIRECT(ADDRESS(ROW()-10;COLUMN())&"":""&ADDRESS(ROW()-1;COLUMN())))"'
# Divide the last two columns
avg='"=INDIRECT(ADDRESS(ROW();COLUMN()-2))/INDIRECT(ADDRESS(ROW();COLUMN()-1))"'
{% endhighlight %}

En estas fórmulas:

* `[ROW()](https://help.libreoffice.org/Calc/Spreadsheet_Functions#ROW)` es el número de la fila actual (puede llevar una referencia). Se le pueden sumar y restar valores, `ROW()-10` hace referencia a la fila menos 10. `COLUMN()` es análogo.  
* `[ADDRESS()](https://help.libreoffice.org/Calc/Spreadsheet_Functions#ADDRESS)` se refiere al nombre de la celda como texto (y por eso se utiliza el `&` para concatenar y las comillas (dobles, para que no se interpreten como las comillas que finalizan la fórmula) para introducir texto...
* `[INDIRECT()](https://help.libreoffice.org/Calc/Spreadsheet_Functions#INDIRECT)` es la referencia especificada por una cadena de texto.

Finalmente, con `SUM` hacemos la suma de esos valores. En las dos líneas de arriba vemos dos ejemplos (el primero podríamos usarlo  para sumar los diez valores de una columna, y el segundo para hacer la división entre el número de valores -no tienen por qué ser válidos todos-).

¿Se podría hacer de otra manera?
Claro, en lugar de los scripts (o con ellos, pero con algo más de trabajo) podríamos incluir las sumas y operaciones en el propio programita.

Otra alternativa sería utilizar sistemas orientados a la generación final del informe, como [Documentos de Latex que incluyen código de R](http://www.uam.es/personal_pdi/ciencias/joser/paginaR/knitr.html) a los que tal vez algún día podamos dedicar algo de nuestro tiempo y paciencia.

¿Otras ideas?
