- [Volver al menú principal](README.md)
- [Regresar a practica 4](practica4.md)
- [Continuar a practica 6](practica6.md)
# Práctica 5 - Introducción a la Inteligencia Artificial: Introspección (con imagen)
### Introducción
El análisis de imágenes es una tarea fundamental en muchos campos, desde la visión por computadora hasta el procesamiento de imágenes médicas. En este ensayo, nos enfocaremos en identificar y contar áreas de color rojo en una imagen utilizando técnicas de procesamiento de imágenes y Python.

### Desarrollo
Para llevar a cabo este análisis, hemos utilizado un código Python que utiliza la biblioteca OpenCV para cargar una imagen y buscar áreas de color rojo contiguas en ella. El algoritmo funciona examinando cada píxel de la imagen y buscando aquellos que estén dentro de un rango de valores de color que consideramos rojos.

El proceso comienza definiendo los límites inferior y superior del color rojo en el formato BGR (Blue, Green, Red) de una imagen. Luego, se recorre cada píxel de la imagen y se comprueba si el color del píxel está dentro del rango establecido para el rojo. Si es así, se inicia un proceso recursivo para marcar todos los píxeles vecinos que también estén dentro del rango de color rojo, formando así una "isla" de color rojo.

El algoritmo cuenta el número de islas encontradas, es decir, el número de áreas de color rojo contiguas en la imagen. Al finalizar, proporciona este recuento como resultado del análisis.

Ejemplo:
Hemos aplicado este código a una imagen específica que contiene áreas de color rojo, como una imagen de un paisaje con elementos rojos dispersos. Al ejecutar el programa, ha identificado y contado estas áreas, ofreciendo el número total de "islas" de color rojo presentes en la imagen.

```python:
import cv2 as cv
import numpy as np

def rojo(pixel, umbral_bajo, umbral_alto):
    return (pixel[2] >= umbral_bajo[0] and pixel[2] <= umbral_alto[0]) and \
           (pixel[1] >= umbral_bajo[1] and pixel[1] <= umbral_alto[1]) and \
           (pixel[0] >= umbral_bajo[2] and pixel[0] <= umbral_alto[2])

def recursivo(img, i, j, ancho, altura):
    if not (i < 0 or i >= ancho or j < 0 or j >= altura):
        if rojo(img[i, j], (100, 0, 0), (255, 100, 100)):
            img[i, j] = [0, 0, 0]
            recursivo(img, i - 1, j, ancho, altura)
            recursivo(img, i + 1, j, ancho, altura)
            recursivo(img, i, j - 1, ancho, altura)
            recursivo(img, i, j + 1, ancho, altura)

islas = 0

map_img = cv.imread('f1.jpg', 1)
ancho_mapa = map_img.shape[0]
altura_mapa = map_img.shape[1]

for i in range(ancho_mapa):
    for j in range(altura_mapa):
        if rojo(map_img[i, j], (100, 0, 0), (255, 100, 100)):
            islas += 1
            recursivo(map_img, i, j, ancho_mapa, altura_mapa)

cv.imshow('Original', map_img)
print('islas:', islas)
cv.waitKey(0)
cv.destroyAllWindows()
```
### Conclusión
Este enfoque proporciona una forma efectiva de identificar áreas de color específicas en imágenes y contar su número. Se puede adaptar para reconocer otros colores o incluso para realizar un análisis más detallado de la distribución espacial de esos colores en una imagen. Esta capacidad tiene aplicaciones significativas en campos como la detección de objetos, la segmentación de imágenes y la identificación de patrones visuales.

- [Volver al menú principal](README.md)