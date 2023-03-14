---
layout: default
title: 04 Principales tipos de archivo
description: Prinicpales tipos de archivo.
Author: Guzman-Diaz, S.; Guzman-Rangel B. 
Maintainer: Guzman-Diaz, S.
Created: March 2023
Last_update: March 2023
---

## Introducción

En esta sección vamos a conocer los principales tipos de archivo que se manejan en un SIG como QGIS. Vamos a clasificarlos en tres tipos distintos: archivos de texto, archivos vectoriales y archivos raster.

## Archivos de texto
Como su nombre indica, estos archivos se componen principalmente de texto plano y consisten principalmente en tablas. La gran mayoría se puede abrir en un editor de texto (como blog de notas, nano, notepad++, etc.) pero comunmente los vizualizamos de una manera más comoda en un programa de hoja de calculo (como Excel, Google Sheets o Calc). 

![texto](assets/images/04.01_texto.png) 
    
     Archivo de texto visto en excel y en un editor de texto

En un contexto geografico, los archivos de texto sólo pueden ser utilizados para representar puntos. Los más simples pueden contener solo dos columnas: coordedana_x y coordenada_y. Sin embargo pueden contener la información adcicional que querramos, por ejemplo: nombre de la especie, familia, nombre de localidad, fecha de colecta, tamaño de población, etc.

Comúnmente, los archivos de texto suelen ser reconocibles por la extensión del archivo (csv, txt, tsv) aunque no siempre es el caso. Algo a tener en cuenta es que aunque parecen iguales a veces pueden tener una codificación distinta (i.e. utf8, ansi, etc.), por lo que si al leer tu archivo ves que en lugar de acentos aparecen symbolos extraños, quizás debes de cambiar la codificación con la que lo estás leyendo.

## Archivos vectoriales

Los archivos vectoriales son una evolución de los archivos de texto. Generalmente la información que contienen también se representa como tablas, pero también tienen propiedades que les permiten representar puntos, lineas y poligonos. Estos archivos pueden ser leídos por un SIG o algunos lenguajes como R o Python y los formatos de archivo más comunmente usados son el shp y el kml (aunque también pueden venir comprimidos en carpetas zip). 

![Vectoriales](assets/images/04.02_vectoriales.png "Ejemplos de archivos vectoriales") 

    Ejemplos de archivos vectoriales: a la izquierda la tabla de un archivo vectorial; a la derecha en rojo puntos; en verde lineas; en azul un poligono

## Archivos raster

El último tipo de archivos que veremos es el archivo raster. Este tipo de archivos es similar a una imagen. Consiste en una matriz o cuadricula de n x m dimensiones. Cada celda de la matriz representa un area determinada (pixel) y contiene un valor que se relaciona a esa area particular. Este tipo de archivos suelen estar en formatos tif, ascii, grd o incluso png.


| ![Raster](assets/images/04.03_raster_01.png) | ![Raster](assets/images/04.03_raster_02.png) 
| ----- | ----- | 
    
    Ejemplo de un archivo raster. A la derecha un acercamiento en donde se observa que el archivo se compone de pixeles.