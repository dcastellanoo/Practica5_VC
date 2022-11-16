# Práctica5 de Visión por Computador

### Contribuyentes:
- Juan Manuel Medina Ramos (juanmamed)
- Diego Castellano Caballero (dcastellanoo)

El objetivo es desarrollar un prototipo de sistema que identifique la matrícula de un vehículo, bien desde una imagen o desde un vídeo. 
Nos centraremos en matrículas españolas, siendo una primera subtarea recopilar o capturar imágenes o vídeos que contengan vehículos con su matrícula visible.
Para poder desarrollar el clasificador usaremos el detector Yolov7 el cual se caracteriza por su velocidad y calidad de detección. Este lo tendremos que entrenar para que pueda detectar matrículas de coches. Una vez entrenado, se le pasarán una serie de imágenes no usadas en el entrenamiento para verificar que este clasifique las matrículas exitósamente. Tras confirmar que este funcione correctamente, se recortaran las matriculas detectadas en la validación. Para ello, se usará el archivo "detect_and_crop.py" del repositorio "https://github.com/RizwanMunawar/yolov7-object-cropping.git" y dichas imágenes las guardarán en la ruta de trabajo.
Para la lectura del texto de las matrículas, se usará Tesseract el cual es un reconocedor de caracteres.

En primer lugar, hemos desarrollado un dataset con diversos imágenes de coches en donde se pueden observar la matrícula delantera y trasera desde diversos ángulos y perspectivas. Este dataset está compuesto por fotografías sacadas por nosotros a través de la cámara del móvil y por imágenes de internet.
Para poder entrenar al detector, tendremos que crear un fichero de texto por imagen, en donde en cada uno se indica la posición en donde se encuentra la matrícula en una de las imágenes, ancho, alto y su clase.
Como observamos que el número de imágenes con el que contábamos en el dataset era muy limitado y para facilitar la generación de los ficheros de texto, usamos roboflow para la creación del dataset que hemos usado.
Una vez creado este, en la configuración del detector hemos tenido tenido que modificar el archivo "yolov7.yaml" indicando que solo tiene que detectar una clase de objeto y añadir el fichero "data.yaml" el cual fue generado en la creación del dataset.
Tras realizar todos estos pasos, ya hemos podido entrenar nuestro detector a través de las imágenes almacenadas en la carpeta de "train" el cual nos ha dado muy buenos resultados. Posteriormente, para confirmar que el detector funciona correctamente se han usado las imágenes del directorio de "valid".
Como se ha comentado anteriormente, hemos recortado las matrículas obtenidas de las imágenes de validación ya que estas son las que leeremos a través del Tesseract. Para facilitar la lectura, se pasan estas a gris.
La ejecución del cuadernos nos mostrará las imagenes de validación con las matriculas marcadas por el detector, las matrículas recortadas y las lecturas de estas.

