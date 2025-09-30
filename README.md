# VC_P2

Práctica realizada por el grupo 15 (Lucía Motas Guedes y Raúl Marrero Marichal)

## Ejercicio 1

Se comienza partiendo de la imagen _[mandril.jpg](https://github.com/ByLucky5/VC_P2/blob/main/mandril.jpg)_ convertida a escala de grises.

Primero obtenemos los contornos con el operador de Canny. Luego realizamos la cuenta de píxeles blancos, por fila y finalmente calculamos el valor máximo de píxeles blancos para filas, _maxfil_, mostrando el número de filas y sus respectivas posiciones, con un número de píxeles blancos mayor o igual que _0.90*maxfil_.

La salida destaca las filas sobre la imagen y sobre una gráfica de cantidad de píxeles blancos respecto a filas, para observar de forma más clara cómo se corresponden los datos de la gráfica con los de la imagen.

## Ejercicio 2

En este ejercicio, se parte de la misma imagen que en el anterior, pero esta vez se utiliza una función gaussiana para suavizar la imagen original, eliminando altas frecuencias. Luego, convertimos la imagen a Sobel de 8 bits y definimos un valor umbralizado.

Se continúa realizando la cuenta de píxeles blancos, por columna y finalmente calculamos el valor máximo de píxeles blancos para columnas, _maxcol_, mostrando el número de columnas y sus respectivas posiciones, con un número de píxeles blancos mayor o igual que _0.90*maxcol_.

La salida las columnas sobre la imagen y sobre una gráfica de cantidad de píxeles blancos respecto a columnas, para observar de forma más clara cómo se corresponden los datos de la gráfica con los de la imagen. Y repetimos el mismo proceso por filas (En lugar de por columnas), igual que en el anterior ejercicio.

---
Se puede observar que los resultados son muy similares entre Canny y Sobel, aunque no idénticos.

Esto se debe a que Canny únicamente indica de manera binaria (true/false) dónde hay un borde si el cambio de color supera cierto umbral establecido mientras que Sobel, calcula un valor en función de la variación de color entre píxeles. Esto permite que, usando Sobel, se pueda determinar los resultados basándose en cúanto han variado de color los píxeles y no en la cantidad de "variaciones" que hay.

Además, Canny realiza la detección de bordes en un solo eje mientras que Sobel, en esta práctica, realiza dicha detección combinando los resultados de ambos ejes.

## Ejercicio 3

En el tercer ejercicio, implementamos un demostrador que nos permite exhibir lo aprendido en estas dos prácticas ante quienes no cursen la asignatura.

El demostrador cuenta con 3 modos diferentes entre los que se puede cambiar pulsando la tecla `espacio`:

1. Vídeo original
2. Umbralizado con valor variable
3. Detección de bordes aplicando Sobel

Todos ellos usan métodos ya usados anteriormente en la práctica, por lo que no es necesario repetir la explicación.

### Controles:
- Tecla `escape`: Cerrar ventana de vídeo
- Tecla `espacio`: Cambiar entre modos de vídeo
- Telca `d`: Aumentar valor de umbral
- Tecla `a`: Reducir valor de umbral

## Ejercicio 4

Para el cuarto ejercicio, se aplica un sustractor de fondo _MOG2_, sobre el vídeo en tiempo real, el cual permite diferenciar las regiones en movimiento del fondo estático de la escena.

Luego, a partir de la máscara resultante, se genera un overlay en color rojo semitransparente que resalta aquellas zonas donde se ha detectado movimiento. Para reforzar la interpretación, se añade un mensaje de advertencia _“WARNING: Movimiento detectado”_ cuando el área del contorno encontrado supera un umbral mínimo, de modo que se ignoren variaciones pequeñas o ruido. Esto permite simular el funcionamiento de una alarma de detección de movimiento.

### Fuentes consultadas

[Documentación - OpenCV](https://docs.opencv.org/4.x/)