---
layout: default
title: 07 Rasters
description: Practica 03 Uso de archivos raster.
Author: Guzman-Diaz, S.; Guzman-Rangel B. 
Maintainer: Guzman-Diaz, S.
Created: March 2023
Last_update: March 2023
---
[Volver al inicio](index.md)

## Introducción

Como mencionamos en la [sección 4](04_archivos.md) las imagenes raster son un tipo de archivo que podemos utilizar en nuestros mapas. Estos se caracterizan por formarse de pixeles y contener datos en forma de bandas. El manejo de estos archivos es un poco distinto del que hemos utilizado para los vectoriales por lo que vale la pena mencionarlos en su propia sección.

## Uso de capas raster

Lo primero que vamos a hacer es cargar una capa raster. En este caso vamos a usar la opción correspondiente de la barra de herramientas Administrar capas. Vamos a utilizar el Continuo de Elevaciones Mexicano (CEM) del estado de Michoacán. Debemos de tener en cuenta que esta capa cuenta con un sistema de referencia llamado ITRF 2008.

Una ves cargado podemos ver los patrones de elevación de todo el estado de michoacán. Esta capa puede ser un poco pesada para algunos equipos. Si este es tu caso te recomiendo que desactives la capa en el panel de Capas haciendo clic en el ☑.

![CEM](assets/images/07.01_cem_mich.png)

Para no tener que lidear con toda la capa, vamos a recortar esta utilizando el poligono del area de estudio que creamos en la [seccion 5](05_Practica_localidades.md). Para esto vamos al menú:

Ráster > Extacción > Cortar raster por capa de máscara...

En la nueva ventana usaremos como capa de entrada el CEM de Michoacán y como máscara el poligono que habíamos creado. En la parte de Advanced Parameters tenemos la opción de guardar la capa como un nuevo archivo o como un archivo temporal. QGIS tiene la capacidad de guardar las capas como archivos temporales, estos son visibles y utilizables mientras el programa esté abierto, sin embargo, una vez que cerramos el programa estas capas son eliminadas. Por el momento dejaremos esta capa como un archivo temporal.

Tras ejecutar la herramienta tendremos la capa recortada a nuestra area de estudio. Nota el icono a la derecha del nombre de la capa que nos avisa que ese es un archivo temporal. En caso de que cambiemos de opinión y querramos guardar la capa en un archivo podemos dar clic derecho en la capa y usar la opción de 
Exportar > Guardar como...

![Cortado](assets/images/07.02_cortado.png)

Si bien esta capa nos da indicios del relieve y la elevación del area, visualmente puede no ser muy informativa. Para mejorar su visualización podríamos entrar a las propiedades de la capa y modificar la simbología de la capa para utilizar otra escala de colores, Esto puede ser muy útil en algunos casos como los modelos de distribución de especies o las variables bioclimaticas. Sin embargo, para un DEM la mejor opción es crear un mapa de sombras (Hillshade) Esto nos permite visualizar el relieve de una manera más clara.

El primer paso para crear un mapa de sombras es contar con un DEM cuyo sistema de referencia esté en metros. Como mencionamos previamente, la capa que estamos utilizando es ITRF 2008, el cúal utiliza coordenadas geográficas. Para poder utilizar esta capa primero la tenemos que reproyectar (es deciir cambiar el sistema de refeerencia que utiliza). Para esto vamos a:

Ráster > Proyecciones > Combar (reproyectar)...

En la ventana que se abre seleccionamos la capa recortada como Capa de entrada y como SRC objetivo vamos a utilizar el EPSG: 32614 - WGS 84 / UTM zone 14N. Este lo vamos a buscar utilizando el icono de la derecha y seleccionamos la opcion de Predefined SRC. De nuevo vamos a dejar esta como una capa temporal. Una ves ejecutada la herramienta deberiamos tener una capa visualmente igual a la que ya teníamos.

El siguiente paso será crear el mapa de sombras, para esto vamos a: 

Ráster > Análisis > Mapa de sombras (Hilshade)...

En esta ventana vamos a elegir la capa que reproyectamos como capa de entrada. En Advances parametros vamos a elegir la opción Guardar a archivo y le daremos nombre a nuestro archivo tiff.

Finalmente vamos a reorganizar las capas y modificaremos la transparencia del mapa de sombras en sus propiedades.

![Sombras](assets/images/07.03_sombras.png)

Con esto podemos regresar al diseñador y crear un nuevo mapa. Para conservar las propiedades del mapa que habíamos creado podemos simplemente hacer una copia de este mapa con las opciones de copiar y pegar. Después sólo debloqueamos las capas y actualizamos la vista para aplicar los cambios. Adicionalmente, modificaremos la cuadricula para quitar las coordenadas y en su lugar utilizaremos un marco de Cebra.

![Mapas](assets/images/07.04_mapas.png)

Para nuestro último mapa vamos utilizar una capa raster de Google Earth. Para esto vamos a utilizar el complemento de QuickMapServices que instalamos. Primero tenemos que habilitar las fuentes en el menú:

Web > QuickMapServices > Settings

En la pestaña More services utilizamos la opción Get contributed pack. Después de unos momentos tendremos habilitadas nuevas opciones en el menú del complemento. Ahora vamos a habilitar los mapas de satelite en:

Web > QuickMapServices > Google

Finalmente podemos ir al diseñador y crear una nueva copia de nuestro mapa. Ahora sólo utilizaremos la herramienta Añadir etiqueta para colocarle etiquetas que identifiquen a cada mapa. Nuestro resultado final quedará de esta forma:

![Mapa final](assets/images/07.05_mapa_final.png)

Lo último que vamos a hacer es exportar nuestra imagen. QGIS nos da un par de opciones para esto. En la parte superior del diseñador tenemos las opciones de Exportar como imagen y Exportar como PDF. Dependiendo de cual va a ser el uso que le den a su mapa pueden utilizar una u otra opción. Algunas revistas cientificas solicitan que los mapas sean exportados como archivos vectoriales o que tengan una cantidad de DPI mínima. En QGIS, exportar como imagen da la posibilidad de escoger la cantidad de PPP (o DPI) que deseen utilizar en su figura. Mientras la opción de exportar en PDF da la posibilidad de exportar como vectorial. Independientemente de la opción escogida, ahora tendrán un mapa visualmente agradable y con las características necesarias para una publicación.


