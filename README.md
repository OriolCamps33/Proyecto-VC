# Proyecto-VC

### Stitching

Primero de todo nos dirigiremos a la carpeta Parts, dentro a la primera carpeta y seguidamente en bda. Ahi veremos un script donde si vamos ejecutando celda por celda conseguiremos ver plots de los diferentes preprocesados de imagenes para intentar mejorar el stitching y finalmente una prueba donde hacemos un stitching con los diferentes procesados de imagenes.

Por otra parte, el otro fichero de stitch se encuentra en el main que es el encargado de generar los stichings de todas las partes las diferentes imagenes.

### Segmentación
Para utilizar la segmentación de imagenes abrimos el archivo Separador.ipynb, las primeras celdas son para la segmentación mediante filtro Otsu, a partir de aqui, las siguientes celdas son usando el algoritmos K-means, la primera genera los datos de entrenamiento del algoritmo, la siguiente entrena el algoritmo, despues se ejecuta el predict para cada imagen a segmentar, visalizamos todas las imagenes segmentadas, finalmente, al ejecutar la ultima celda, esta guardar la imagenes de la sustancia blanca en una carpeta llamada S_blanca.

### Detección de axones
Para hacer la detección de axones habrá que usar el fichero axones.ipynb. La primera celda lee las imágenes de la carpeta S_blanca. Las 3 siguientes celdas sirven para aplicar la detección y el conteo de los axones a todas las imágenes, cada celda con un método. La primera usa un detector de blobs, la segunda lo hace con un threshold y un opening y la tercera añade el opening residue. Los outputs darán información sobre el precision y el recall para cada imagen y en general.
Además, se guardaran imágenes con el resultado dentro de la carpeta Detector_axons, donde habrá otra carpeta para cada método. En la imagen, los círculos azules representan los axones detectados correctamente (True Positives), los círculos verdes son los axones detectados por error (False Positives) y los círculos blancos son los axones no detectados (False Negatives).