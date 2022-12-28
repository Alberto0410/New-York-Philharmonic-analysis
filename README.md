# Análisis del dataset del historial de presentaciones de la filarmónica de Nueva York.

En este proyecto se hizo un análisis del [dataset](https://www.kaggle.com/datasets/nyphil/perf-history) de las presentaciones de la orquesta filarmónica de Nueva York
desde 1842

## Objetivo

El objetivo de dicho análisis es responder preguntas relevantes como por ejemplo:
* Quienes son los compositores más famosos?
* Hay alguna tendencia hacia una corriente musical? Predomina el barroco, clasicismo, romanticismo o algun otro? 
* Los directores de orquesta tienen compositores favoritos?
* La Orquesta Filarmónica de Nueva York está tocando música de compositores contemporaneos?
* Los compositores tiene épocas de fama?

## Procedimiento
Se procedio primero con la limpieza del dataset y el tratamiento de los datos para posteriormente manipularlo. En esta sección se hizo uso de las librerias padas y
numpy. Para poder visulizar los datos se utilizo la libreria Plotly.


Al transformar la columna de compositores a una variable categórica, obtenemos una manera mucho más sencilla de manejar los datos como lo muestra el siguiente histograma

![bar_comp](https://user-images.githubusercontent.com/79923122/209861111-5060b13b-2237-4450-b13c-b60d64a76cfa.PNG)

Posteriormente se procedió a realizar una función que dado el nombre de un compositor y un intervalo de tiempo, regresa como resultado un histograma de qué tantas veces
dicho artista fue tocado en la orquesta. De manera similar se hizo otra función que graficara el top de compositores más tocados en un rango de tiempo. 

Con dichas herramientas en mano se pudo contestar a la pregunta se si hubo/hay tendencias hacia alguna corriente musical. Por ejemplo, para estudiar el barroco basta con tomar a los compositores más representativos del movimiento, como por ejemplo Johann Sebastian Bach, Handel, etc. y así poder ver si hay alguna época en donde sus obras fueron más ejecutadas. Una vez hecho lo anterior podemos identificar intervalos de tiempo en donde ambos compositores tuvieron más fama y procedemos a usar la segunda función para ver qué compositores fueron más tocado en esas fechas.

![hist_bach](https://user-images.githubusercontent.com/79923122/209861780-49876e9f-ad2e-415f-8b73-b35f664ef95c.PNG)

El mismo procedimineto se realiza con las otras corrientes musicales.

Luego, el compositor Beethoven es un elemento importante debido a que tiene obras tanto del clasicismo como del romanticismo, entonces es interesante preguntarse si 
es más reconocido por su periodo clásico o no. Para responder a dicha pregunta procedemos a realizar un histograma de sus obras más ejecutadas

![obras_beethoven](https://user-images.githubusercontent.com/79923122/209862956-84e34b1f-09b1-495a-8414-b059994da81a.PNG)

Al momento de pasar con los artístas contemporaneos tomamos el caso particular de Stravinsky, pues es uno de los representantes más grandes de dicha corriente. 
A lo largo de este projecto unicamente se han tratado las obras orquestales, por lo que sería interesante analizar las obras de ballet y el mejor candidato para 
hacerlo es Stravinsky debido a sus grandes aportaciones al ballet como lo son sus tres obras Petrushka, La Consagración de la Primavera y el Pájaro de Fuego, todas 
ellas obras revolucionarias.

![ballets stra](https://user-images.githubusercontent.com/79923122/209863243-95ef0962-4bef-4c63-9554-52e3ef323292.PNG)

Finalmente, obtenemos el siguiente histograma de los compositores más tocados en el siglo XX 

![siglo XX](https://user-images.githubusercontent.com/79923122/209863292-4358f7f6-a29c-4c0f-bfa3-3f147fa5bac4.PNG)

Para responder a la pregunta de si los directores tienen compositores favoritos basta con filtrar el dataset por el nombre del director deseado y posteriormente usar 
la función que nos regresa el top de los artistas más tocados en un intervalo de tiempo. Para esta pregunta es interesante tomar los casos de Bernstein y de Mahles, 
los cuales fueron tanto compositores muy reconocidos como directores de la Filarmónica de NY.


Por último, para ver si dicha orquesta está tocando música de nuevos artistas basta con analizar su repertorio de los últimos 20 años con la función mencionada al 
inicio del documento

## Resultados
Hablando del compositor Bach notamos que no tuvo mucha fama debido a que sus obras no eran muy conocidad. No fue hasta que Mendelssohn redescubrió la música de Bach (aproximadamente en 1829) cuando su popularidad empezó a subir hasta llegar al punto de auge aproximadamente en 1940

Por otro lado, la corriente musical que predominó en 1900 y 1950 fue el romanticismo, liderado por Wagner, Beethove, Tchaikovsky, Brahms, etc. A pesar de lo ya 
mencionado, en el top de compositores más tocados en dicha epoca podemos encontrar tanto representantes del barroco como del clasicismo.

Hablando del Tchaikovsky podemos decir que, como la mayoría de compositores, no fue muy reconocido en su época como lo fue posteriormente. Dicho artista vivió entre 
1840 y 1893 y su popularidad llegó a inicios del siguiente siglo

Al analizar los histogramas de los compositores notamos que a veces hay picos de popularidad muy pronunciados los cuales en su mayorita son debidos a algun aniversario
de muerte o a algun evento social.

Luego, al analizar las obras de Beethoven concluimos que es más reconocido por sus obras del periodo romántico que por las del clásico

Continuando con el periodo contemporaneo, en particular con Stravinsky, podemos destacar que su ballet más tocado es El Pájaro de Fuego, lo cual es sorpresivo debido 
a que uno pensaría que el más famoso es La Consagración de la Primavera debido a sus implicaciones en el repertorio musical. Cabe destacar que en el 2010 hubo un gran 
aumento en el número de ejecuciones del Pájaro de Fuego, lo cual es debido a que en dicho año se cumplió el aniversario número 100 de su estreno en Paris

Los compositores más tocados en el siglo XX fueron Bernstein y George Gershwin, dejando muy por detrás a los demás artistas, lo cual es impresionante debido a que no 
tuvieron el reconocimiento que se deberia a personajes como por ejemplo Shostakovich, Shoenberg, Britten, John Cage, Duke Ellington, etc.

Cambiando de pregunta, podemos decir que los directores sí tienen compositores preferidos, como lo es el caso de Bernstein, quien fue un personaje clave para resucitar 
las obras de Mahler, lo cual se ve reflejado ya que dicho compositor es el número 9 en el top de más tocados por Bernstein. 

Finalmente, al analizar los últimos 20 años de la orquesta notamos que hay un cierto equilibrio entre las corrientes musicales, pues hay tanto compositores del barroco 
como del clacisismo, romanticismo y el movimiento contemporaneo. La mala noticia es que en top no se encuentra ningun compositor que siga vivo. 

Bajando en el top encontramos en la posición 33 a John Williams, famoso por sus bandas sonoras. En el lugar número 44 encontramos a Stephen Sondheim quien desafortunadamente falleció en el 2021, pero lo metemos dentro de la lista ya que el dataset tiene información hasta 2017.
En el puesto 54 está Chistopher Rouse quien falleció igualmente en el 2021 pero lo dejamos en la lista por la misma razón que se mencionó anteriormente

En el lugar 56 está Magnus Lindberg y en el 57 Esa-Pekka Salonen

A pesar de que sí hay compositores contemporaneos a nosotros siendo famosos en las salas de conciertos, no son muchos, es decir que trsitemente no hay mucha música actual siendo tocada. Esperemos que lo anterior se deba al fenómeno ya visto en este breve análisis, es decir, que en un par de años en los programas musicales van a predominar compositores de ésta época
