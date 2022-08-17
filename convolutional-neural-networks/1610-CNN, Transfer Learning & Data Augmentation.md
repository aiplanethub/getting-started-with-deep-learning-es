## Objetivos de aprendizaje

* Invariancia espacial/traslación
* Desventajas de MLP
* Red neuronal convolucional
* Comparación de la arquitectura CNN y ANN/MLP
* Aprendizaje profundo en datos limitados: aprendizaje de transferencia, aumento de datos
* Normalización de lotes de datos


Hasta ahora, ha trabajado con perceptrones multicapa (MLP).

Los MLP son excelentes para MNIST, un conjunto de datos más simple y directo, pero están rezagados con respecto a las CNN cuando se trata de aplicaciones del mundo real en visión artificial, específicamente clasificación de imágenes.

Los conceptos que hacen que CNN sea tan genial no son complejos, pero son muy intuitivos, lógicos y fáciles de entender.

## Invariancia espacial/traslación
La invariancia espacial o de traducción significa que si un objeto aparece en cualquier imagen, se detectará independientemente de su posición.

Un gato sigue siendo un gato independientemente de si aparece en la mitad superior o inferior de la imagen.








![imagen.png](https://dphi-live.s3.amazonaws.com/media_uploads/image_9f667ea28fba4324902ae5d06d8d8907.png)







## Desventajas de MLP
* Necesidad de conectar las neuronas en la capa oculta a TODAS las neuronas en la capa de entrada
* Sin información espacial: dado que remodelamos la imagen de 2D a 1D, no comprende la estructura espacial de la imagen, es decir, no es espacialmente invariable. Por ejemplo, si aparece la imagen de un gato en la parte superior izquierda de la imagen en una imagen y en la parte inferior derecha de otra imagen, el MLP intentará corregirse y supondrá que siempre aparecerá un gato en esta sección de la imagen.





![imagen.png](https://dphi-live.s3.amazonaws.com/media_uploads/image_0415b77cff744bc7b422e6c4e385f2ff.png)





* Y muchos, muchos parámetros a manejar. Los MLP usan un perceptrón para cada entrada (por ejemplo, píxel en una imagen, multiplicado por 3 en el caso de RGB). La cantidad de pesos rápidamente se vuelve inmanejable para imágenes grandes. Para una imagen de 224 x 224 píxeles con tres canales de color, ¡se deben entrenar alrededor de 150 000 pesos!

## La red neuronal convolucional

Las redes neuronales convolucionales están diseñadas para ser espacialmente invariantes; no son sensibles a la posición del objeto en la imagen. ¡El gato puede estar en cualquier parte de la imagen y aun así lo reconocerá!

Pero, ¿y si la imagen no consiste solo en un gato? ¿Qué pasa si hay más características? ¿Voltear la imagen confundirá a la CNN? ¡No, una CNN seguirá funcionando bien!

Las CNN aprovechan el hecho de que los píxeles cercanos están más fuertemente relacionados que los distantes. Entonces, los píxeles alrededor del cielo seguirán siendo cielo, y los píxeles cerca de un girasol tienen más posibilidades de ser un girasol.



![imagen.png](https://dphi-live.s3.amazonaws.com/media_uploads/image_4880b5757ed24112bc9d6c6ecec951f8.png)



Para enseñar un algoritmo a reconocer objetos en imágenes, utilizamos un tipo específico de Red Neuronal Artificial: una Red Neuronal Convolucional (CNN). Su nombre proviene de una de las operaciones más importantes de la red: la convolución.

La palabra convolución se refiere al proceso de filtrado que ocurre en este tipo de red. En términos literales, es una operación matemática que hace posible el filtrado.

## Comparación de CNN y ANN/MLP

Redes neuronales regulares:

* Transforme una entrada al pasarla por una serie de capas ocultas.
* Cada capa se compone de un conjunto de neuronas, donde cada capa está completamente conectada a todas las neuronas de la capa anterior.
* Finalmente, hay una última capa totalmente conectada, la capa de salida, que representa las predicciones.

En las CNN:
* Las capas están organizadas en 3 dimensiones: ancho, alto y profundidad.
* Las neuronas de una capa no se conectan con todas las neuronas de la siguiente capa, sino solo con una pequeña región.





![imagen.png](https://dphi-live.s3.amazonaws.com/media_uploads/image_4b16928c40f54af8b69b35d289e5d874.png)




## CNN Trabajando
### Componentes CNN

Las CNN tienen dos componentes:

1. La parte de extracción de características/capas ocultas
En esta parte, la red realizará una serie de operaciones durante las cuales se detectan las características. Si tuviera una imagen de una cebra, esta es la parte donde la red reconocería sus rayas, dos orejas y cuatro patas.
2. La parte de Clasificación
Esta parte asigna una probabilidad de que el objeto (por ejemplo, la cebra) esté en esa imagen.






![imagen.png](https://dphi-live.s3.amazonaws.com/media_uploads/image_12e471c9f8a74106b99f9a5b60045d84.png)





### Una arquitectura CNN básica

A continuación se muestra el orden básico de operaciones en una CNN. Las operaciones de convolución y agrupación pueden ocurrir varias veces en una CNN; el orden, sin embargo, seguirá siendo el mismo. Siempre serán reemplazadas por capas Totalmente Conectadas y Softmax/Sigmoid.






![imagen.png](https://dphi-live.s3.amazonaws.com/media_uploads/image_96067a23b48f476db2426bff116896da.png)











### Comprensión básica de filtro, zancada y convolución

Esto explica brillantemente cómo un kernel/filtro hace posible la convolución. Para las personas preocupadas por cómo exactamente se obtiene un tamaño particular al aplicar un kernel en una matriz, esto resolverá su confusión.






<iframe width="560" height="315" src="https://www.youtube.com/embed/Qj_LJQj09Ps" title="Reproductor de video de YouTube" frameborder="0" allow="acelerómetro; reproducción automática; portapapeles- escribir; medios cifrados; giroscopio; imagen en imagen" allowfullscreen></iframe>









### ¿Qué es el relleno cero y por qué es necesario?












<iframe width="560" height="315" src="https://www.youtube.com/embed/qSTv_m-KFk0" title="Reproductor de video de YouTube" frameborder="0" allow="acelerómetro; reproducción automática; portapapeles-escribir; medios cifrados; giroscopio; imagen en imagen" allowfullscreen></iframe>












### Agrupación máxima










<iframe width="560" height="315" src="https://www.youtube.com/embed/ZjM_XQa5s6s" title="Reproductor de video de YouTube" frameborder="0" allow="acelerómetro; reproducción automática; portapapeles- escribir; medios cifrados; giroscopio; imagen en imagen" allowfullscreen></iframe>









### ¿Qué aprenden las capas de CNN?
* Cada capa de CNN aprende filtros de complejidad creciente.
* Las primeras capas aprenden filtros básicos de detección de características: bordes, esquinas, etc.
* Las capas intermedias aprenden filtros que detectan partes de objetos. Para las caras, pueden aprender a responder a los ojos, narices, etc.
* Las últimas capas tienen representaciones más altas: aprenden a reconocer objetos completos, en diferentes formas y posiciones.








![imagen.png](https://dphi-live.s3.amazonaws.com/media_uploads/image_e9356cd8e9384b1ea851b5985cd2e36c.png)









Las funciones anteriores de ConvNet contienen funciones más genéricas (por ejemplo, detectores de bordes o detectores de manchas de color), pero las capas posteriores de ConvNet se vuelven cada vez más específicas para los detalles de las clases contenidas en el conjunto de datos original.

## Cómo usar Deep Learning cuando tienes datos limitados

### El problema de los datos limitados

_"La analogía con el aprendizaje profundo es que el motor del cohete son los modelos de aprendizaje profundo, y el combustible son las enormes cantidades de datos que podemos alimentar a estos algoritmos"._ — Andrew Ng

Ha habido un aumento reciente en la popularidad del aprendizaje profundo, logrando un rendimiento de vanguardia en varias tareas como traducción de idiomas, juegos de estrategia y autos sin conductor que requieren millones de puntos de datos.

Una barrera común para usar el aprendizaje profundo para resolver problemas es la cantidad de datos necesarios para entrenar un modelo. El requisito de grandes datos surge debido a la cantidad de parámetros en el modelo que las máquinas tienen que aprender.


Entonces, ¿qué haces cuando no puedes encontrar los datos requeridos mientras trabajas en un problema?

## ¡Transfiere el aprendizaje al rescate!

"Si Deep Learning es el santo grial y los datos son el guardián, transferir el aprendizaje es la clave".

### Transferencia de aprendizaje
El aprendizaje por transferencia utiliza el conocimiento adquirido al resolver un problema y aplicarlo a un problema diferente pero relacionado.

Por ejemplo, el conocimiento adquirido al aprender a reconocer automóviles se puede utilizar hasta cierto punto para reconocer camiones.





![imagen.png](https://dphi-live.s3.amazonaws.com/media_uploads/image_14a24b1e978044f4b07c062c68a0712d.png)















<iframe width="560" height="315" src="https://www.youtube.com/embed/5T-iXNNiwIs" title="Reproductor de video de YouTube" frameborder="0" allow="acelerómetro; reproducción automática; portapapeles-escribir; medios cifrados; giroscopio; imagen en imagen" allowfullscreen></iframe>











#### Pre-entrenamiento

Cuando entrenamos una red en un gran conjunto de datos (por ejemplo, ImageNet), entrenamos todos los parámetros de la red neuronal y, por lo tanto, se aprende el modelo. Puede tomar horas en su GPU para entrenar en un conjunto de datos tan grande. Este modelo se conoce como modelo preentrenado.

#### Sintonia FINA
Podemos proporcionar el nuevo conjunto de datos para afinar la CNN preentrenada. Tenga en cuenta que el nuevo conjunto de datos es casi similar al conjunto de datos original utilizado para el entrenamiento previo. Dado que el nuevo conjunto de datos es similar, se pueden usar los mismos pesos para extraer las características del nuevo conjunto de datos.
1. Si el nuevo conjunto de datos es muy pequeño, es mejor entrenar solo las capas finales de la red para evitar el sobreajuste, manteniendo todas las demás capas fijas. Por lo tanto, elimine las capas finales de la red preentrenada y agregue otras nuevas. Vuelva a entrenar solo las nuevas capas.
2. Si el nuevo conjunto de datos es grande, vuelva a entrenar toda la red con pesos iniciales del modelo previamente entrenado.

Otra gran ventaja de usar el aprendizaje por transferencia es qué tan bien se generaliza el modelo.

Los modelos más grandes tienden a sobreajustar los datos y no funcionan bien cuando se prueban con datos ocultos. Dado que el aprendizaje por transferencia permite que el modelo vea diferentes tipos de datos, aprende mejor las reglas subyacentes del mundo.


Puedes ver este video si está interesado en aprender cómo se realiza Transfer Learning. Es un tema un poco avanzado, así que no te preocupes si no lo entiendes a la primera. Además, el instructor está usando Keras, pero el mismo código también funcionará con tf.Keras.





<iframe width="560" height="315" src="https://www.youtube.com/embed/oDHpqu52soI?start=71" title="Reproductor de video de YouTube" frameborder="0" allow="acelerómetro; reproducción automática; escritura en el portapapeles; medios cifrados; giroscopio; imagen en imagen" allowfullscreen></iframe>









## Aumento de datos
Necesitamos modificaciones menores a nuestro conjunto de datos existente para acumular más datos, cambios menores como volteos, traslaciones o rotaciones. Y nuestra red neuronal pensará que estas son imágenes distintas de todos modos.

Se dice que una red neuronal convolucional que puede clasificar objetos de manera robusta, incluso si se colocan en diferentes orientaciones, tiene la propiedad llamada invariancia. Más específicamente, una CNN puede ser invariable a la traducción, el punto de vista, el tamaño o la iluminación (o una combinación de los anteriores).

Esta es esencialmente la premisa del aumento de datos. En un escenario del mundo real, podemos tener un conjunto de datos de imágenes tomadas en un conjunto limitado de condiciones. Sin embargo, nuestra aplicación de destino puede existir en varias condiciones, como orientación, ubicación, escala, brillo, etc. Damos cuenta de estas situaciones entrenando nuestra red neuronal con datos adicionales modificados sintéticamente.

¡También es uno de los métodos para evitar el sobreajuste!

_Tu red neuronal es tan buena como los datos que la alimentas._

Realizar el aumento puede evitar que su red neuronal aprenda patrones irrelevantes, lo que esencialmente aumenta el rendimiento general.

Su modelo para detectar una mariposa debería poder encontrar una mariposa en la imagen incluso si está volando hacia los lados, ¿verdad?




![imagen.png](https://dphi-live.s3.amazonaws.com/media_uploads/image_14468a4be2904801a4d8df731197631a.png)




### Técnicas de aumento populares en imágenes

1. Voltear - horizontal/verticalmente
2. Rotación
3. Escala
4. Recortar
5. Traducción
6. Color variable
7. Agregar ruido
8. Ajuste de brillo

Aparte de lo anterior, muchas más técnicas de aumento
existir.

### ¿Dónde realizar el aumento de datos?

El aumento de datos generalmente se realiza en el conjunto de trenes y, a menudo, en el conjunto de validación. Esto se debe a que queremos aumentar el tamaño y la variedad de datos de los que aprende nuestro modelo.

Sin embargo, el aumento de datos también se puede realizar en el conjunto de prueba. No es para hacer que los datos de prueba sean más grandes o más precisos, sino para hacer que los datos de entrada del conjunto de prueba se parezcan a los datos de entrada del conjunto de entrenamiento para que podamos introducirlos en la misma red (por ejemplo, las mismas dimensiones).

Por ejemplo, en el recorte de imágenes, necesitaríamos recortar las imágenes de prueba
también, por lo que son de un tamaño similar a las imágenes de entrenamiento.

### ¿Cómo realizar el aumento de datos?

Una función de Tensorflow Keras llamada ImageDataGenerator ayuda en
realizar técnicas de aumento de datos.

Un ImageDataGenerator que realiza el aumento podría tener este aspecto:

```
train_datagen = ImageDataGenerator(
    rango_de_rotación=20,
    ancho_cambio_rango=0.2,
    altura_cambio_rango=0.2,
    cortante_rango=0.2,
    zoom_rango=0.2,
    horizontal_flip=Verdadero
    vertical_flip=Verdadero,
    fill_mode='más cercano')
```

¡Mira la variedad de operaciones de aumento disponibles!

Nota: además de ImageDataGenerator, existen muchas otras opciones para realizar el aumento de datos.








<iframe width="560" height="315" src="https://www.youtube.com/embed/0ronGSOsEtY?start=87" title="reproductor de video de YouTube" frameborder="0" allow="acelerómetro; reproducción automática; escritura en el portapapeles; medios cifrados; giroscopio; imagen en imagen" allowfullscreen></iframe>








## Normalización por lotes: hacer que los modelos sean más rápidos y estables

### Normalización por lotes: ¿Qué y por qué?










<iframe width="560" height="315" src="https://www.youtube.com/embed/DtEq44FTPM4" title="Reproductor de video de YouTube" frameborder="0" allow="acelerómetro; reproducción automática; portapapeles- escribir; medios cifrados; giroscopio; imagen en imagen" allowfullscreen></iframe>












### Normalización por lotes: ¿Cómo?

Aplicar la normalización por lotes es tan simple como agregar una capa llamada BatchNormalization() después de la capa de convolución. Se puede agregar a cualquier red neuronal.

```
# Crear el modelo modelo = Secuencial()
modelo.add(Conv2D(32, tamaño del kernel=(3, 3), activación='relu', forma de entrada=forma_entrada)
modelo.add(Normalización por lotes())
modelo.add(MaxPooling2D(pool_size=(2, 2)))
modelo.add(Normalización por lotes())
modelo.add(Conv2D(64, kernel_size=(3, 3), activación='relu'))
modelo.add(Normalización por lotes())
modelo.add(MaxPooling2D(pool_size=(2, 2)))
modelo.add(BatchNormalization()) modelo.add(Flatten()) modelo.add(Dense(256, activación='relu'))
modelo.add(Normalización por lotes())
modelo.add(Dense(sin_clases, activación='softmax'))
```


### Material adicional

Un buen artículo que arroja luz sobre la variedad de técnicas de aumento de datos en la práctica:
https://towardsdatascience.com/exploring-image-data-augmentation-with-keras-and-tensorflow-a8162d89b844

### Enlace de descarga de diapositivas

Puede descargar las diapositivas de este módulo desde [aquí](https://docs.google.com/presentation/d/1gay6jH7mfZIRjAPtt9gDqKoAlx5wSaDOEbDtmQToUAY/edit?usp=sharing).

### Referencias

* https://towardsdatascience.com/what-is-transfer-learning-8b1a0fa42b4
* https://medium.com/nanonets/nanonets-how-to-use-deep-learning-when-you-have-limited-data-f68c0b512cab
* https://nanonets.com/blog/data-augmentation-how-to-use-deep-learning-when-you-have-limited-data-part-2/