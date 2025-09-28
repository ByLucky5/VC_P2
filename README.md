# VC_P2

Práctica realizada por el grupo 15 (Lucía Motas Guedes y Raúl Marrero Marichal)

## Ejercicio 1

Se comienza partiendo de la imagen _[mandril.jpg](https://github.com/ByLucky5/VC_P2/blob/main/mandril.jpg)_ convertida a escala de grises.

Primero obtenemos los contornos con el operador de Canny. Luego realizamos la cuenta de píxeles blancos, por fila y finalmente calculamos el valor máximo de píxeles blancos para filas, maxfil, mostrando el número de filas y sus respectivas posiciones, con un número de píxeles blancos mayor o igual que 0.90*maxfil.

La salida destaca las filas sobre la imagen y sobre una gráfica de cantidad de píxeles blancos respecto a filas, para observar de forma más clara cómo se corresponden los datos de la gráfica con los de la imagen.

## Ejercicio 2

En este ejercicio, se parte de la misma imagen que en el anterior, pero esta vez se utiliza una función gaussiana para suavizar la imagen original, eliminando altas frecuencias. Luego, convertimos la imagen a Sobel de 8 bits y definimos un valor umbralizado.

Se continúa realizando la cuenta de píxeles blancos, por columna y finalmente calculamos el valor máximo de píxeles blancos para columnas, maxcol, mostrando el número de columnas y sus respectivas posiciones, con un número de píxeles blancos mayor o igual que 0.90*maxcol.

La salida las columnas sobre la imagen y sobre una gráfica de cantidad de píxeles blancos respecto a columnas, para observar de forma más clara cómo se corresponden los datos de la gráfica con los de la imagen. Y repetimos el mismo proceso por filas (En lugar de por columnas), igual que en el anterior ejercicio.

## Ejercicio 3

En el tercer ejercicio, implementamos un demostrador que nos permite exhibir lo aprendido en estas dos prácticas ante quienes no cursen la asignatura. En nuestro caso escogimos un primer modo que muestre el umbralizado de la imagen y se puede modificar el valor de umbral mediante las teclas a (disminuye el valor de umbralizado) y d (lo aumenta). Para el segundo modo, mostramos cómo se ve la imagen tras aplicarle Sobel.

## Ejercicio 4

Para el cuarto ejercicio, se aplica un sustractor de fondo MOG2, sobre el vídeo en tiempo real, el cual permite diferenciar las regiones en movimiento del fondo estático de la escena.

Luego, a partir de la máscara resultante, se genera un overlay en color rojo semitransparente que resalta aquellas zonas donde se ha detectado movimiento. Para reforzar la interpretación, se añade un mensaje de advertencia “WARNING: Movimiento detectado” cuando el área del contorno encontrado supera un umbral mínimo, de modo que se ignoren variaciones pequeñas o ruido.

### Fuentes consultadas
