## Objetivos de aprendizaje

* ¿Cómo ven las computadoras las imágenes?
* Visión por computador
* CV abierto

## ¿Cómo ven las imágenes las computadoras?

Cuando vemos esta imagen, podemos decir, sin siquiera pensarlo, que se trata de una imagen de un perro adorable. Incluso un niño de 8 años no tendría ningún problema en identificar al perro de la imagen.









![imagen.png](https://dphi-live.s3.amazonaws.com/media_uploads/image_15a3c79a17424048917a6078da0cd966.png)










### Píxel
¿Alguna vez te has preguntado cómo una computadora ve esa misma imagen?

Una computadora ve una imagen como 0 y 1 (dígitos binarios).
El píxel es la unidad más pequeña de una imagen.






![imagen.png](https://dphi-live.s3.amazonaws.com/media_uploads/image_60303e4331d84b73bbd17d5e75244f2a.png)






Diagrama de datos de píxeles. A la izquierda hay una imagen de Lincoln. En el centro, los píxeles están etiquetados de 0 a 255, lo que representa su nivel de brillo y a la derecha están los mismos números. Pero, ¿Qué es este 0-255? Son valores de combinación de colores en RGB; pronto aprenderemos qué es RGB.




![imagen.png](https://dphi-live.s3.amazonaws.com/media_uploads/image_1b0d92842bab4a4eb106ba575dc2a9cb.png)





Aquí, la oreja del animal se ha ampliado para mostrar un píxel de la imagen.

### Canales

Las computadoras son incapaces de reconocer o mirar imágenes de la forma en que lo haríamos los humanos. Entonces, tenemos que encontrar una manera de convertir estas imágenes en números. Hay dos formas comunes de hacer esto cuando se trata de procesamiento de imágenes:
1. **Escala de grises**: una gama de tonos grises desde el blanco hasta el negro.
Al usar la escala de grises, la computadora asigna a cada píxel un valor (en números) basado en su nivel de oscuridad.
2. **Valores RGB**: una combinación de rojo (Red), verde (Green) y azul (Blue), de ahí el R-G-B.
Una vez que se le asigna un valor RGB al color, la computadora extrae ese valor de cada píxel y coloca los resultados en una matriz.

Cada píxel contiene un número diferente de canales, y los canales están asociados a representaciones numéricas. Si es una imagen en escala de grises, tiene un solo canal (un número que lo representa), mientras que si es una imagen en color, el pixel contiene tres canales: rojo, verde y azul (tres números que lo representan).




| ![imagen.png](https://dphi-live.s3.amazonaws.com/media_uploads/image_fff853435a574068927daaf08569f15c.png) | ![imagen.png](https://dphi-live.s3.amazonaws.com/media_uploads/image_392006567fce44e0b69258d1f9dc400e.png) |
| --- | --- |






Como se muestra en la representación anterior de una imagen digital en color, cada canal de píxeles tiene un valor entre 0 y 255.

### Comprender las imágenes en color

Para cualquier imagen en color en formato RGB, hay tres canales principales: rojo, verde y azul. Cómo funciona es bastante simple.

Se forma una matriz para cada color primario y luego estas matrices se combinan para proporcionar un valor de píxel para los colores R, G y B individuales.

Considere la siguiente imagen:





![imagen.png](https://dphi-live.s3.amazonaws.com/media_uploads/image_5b6aa9091df94fde89643e97c2842dbe.png)






Nota: También existen imágenes con 4, 5 o más canales. Una imagen puede tener hasta 56 canales.

Por ejemplo, las imágenes en la edición de gráficos sofisticados utilizan cuatro canales: tres canales para RGB más un canal alfa o "a" adicional.

Además, una imagen CMYK tiene cuatro canales: cian, magenta, amarillo y clave (negro).

Cuando decimos tres canales, consideramos imágenes de tipo RGB.

### Representación de imágenes

Las imágenes generalmente se representan como Alto x Ancho x #Canales, donde #Canales es 3 para imágenes RGB y 1 para imágenes en escala de grises.

A veces ves Ancho x Alto x #Canales, pero el tercero
dimensión son los "canales".

El tamaño de la imagen en la diapositiva anterior se puede calcular como
B x A x 3.

¿Puedes ahora entender por qué? (# significa el número de algo)





<iframe width="560" height="315" src="https://www.youtube.com/embed/LLAgPtpZth8?start=14" title="Reproductor de video de YouTube" frameborder="0" allow="acelerómetro; reproducción automática; escritura en el portapapeles; medios cifrados; giroscopio; imagen en imagen" allowfullscreen></iframe>









La siguiente pregunta es, ¿cómo podemos decir que la imagen contiene la imagen de un perro?

Solo leer la imagen es inútil si no puede entender lo que significa o si no puede describir de qué se trata la imagen y qué contiene. Aquí es donde entra el aprendizaje automático.

A una máquina (oa una computadora) se le puede enseñar cómo entender una imagen y decir qué contiene la imagen. Este es un ejemplo de aprendizaje automático que le enseña a una computadora a comprender y describir una imagen. Es similar a cómo enseñamos a los niños a identificar diferentes alfabetos o diferenciar entre una manzana y un plátano mostrando ejemplos de cada caso. Así es exactamente como una computadora aprende a identificar objetos en una imagen.

Al igual que los humanos tienen diferentes habilidades, y una de las habilidades es identificar un objeto en una imagen (un perro en la imagen de arriba), las computadoras tienen modelos de aprendizaje automático, que pueden considerarse como una habilidad, para realizar la misma tarea. Como los humanos necesitan ser entrenados para realizar una habilidad particular, las computadoras también necesitan entrenar el modelo de aprendizaje automático.

En ambos casos, el entrenamiento ocurre usando ejemplos. De manera similar a cómo se le enseña a un niño a identificar una manzana, a un modelo de aprendizaje automático se le puede enseñar cómo identificar una manzana en una imagen al proporcionar varias imágenes que contienen una aplicación.