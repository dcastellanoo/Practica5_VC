# Práctica5 de Visión por Computador

### Contribuyentes:
- Juan Manuel Medina Ramos (juanmamed)
- Diego Castellano Caballero (dcastellanoo)

El objetivo es desarrollar un prototipo de sistema que identifique la matrícula de un vehículo, bien desde una imagen o desde un vídeo. 
Nos centraremos en matrículas españolas, siendo una primera subtarea recopilar o capturar imágenes o vídeos que contengan vehículos con su matrícula visible.
Para poder desarrollar el clasificador usaremos el detector Yolov7 el cual se caracteriza por su velocidad y calidad de detección. Este lo tendremos que entrenar para que pueda detectar matrículas de coches.

En primer lugar, hemos desarrollado un dataset con diversos imágenes de coches en donde se pueden observar la matrícula delantera y trasera desde diversos ángulos y perspectivas.
Para poder entrenar al detector, tendremos que crear un dataset de ficheros de texto, a partir del generado anteriormente, en donde en cada uno se indica la posición en donde se encuentra la matrícula en una de las imágenes y su clase.
