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
Alto x Ancho x 3.

¿Puedes ahora entender por qué? (# significa el número de algo)





<iframe width="560" height="315" src="https://www.youtube.com/embed/LLAgPtpZth8?start=14" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>









La siguiente pregunta es, ¿cómo podemos decir que la imagen contiene la imagen de un perro?

Solo leer la imagen es inútil si no puede entender lo que significa o si no puede describir de qué se trata la imagen y qué contiene. Aquí es donde entra el aprendizaje automático.

A una máquina (una computadora) se le puede enseñar cómo entender una imagen y decir qué contiene la imagen. Este es un ejemplo de aprendizaje automático que le enseña a una computadora a comprender y describir una imagen. Es similar a cómo enseñamos a los niños a identificar diferentes alfabetos o diferenciar entre una manzana y un plátano mostrando ejemplos de cada caso. Así es exactamente como una computadora aprende a identificar objetos en una imagen.

Al igual que los humanos tienen diferentes habilidades, y una de las habilidades es identificar un objeto en una imagen (un perro en la imagen de arriba), las computadoras tienen modelos de aprendizaje automático, que pueden considerarse como una habilidad, para realizar la misma tarea. Como los humanos necesitan ser entrenados para realizar una habilidad particular, las computadoras también necesitan entrenar el modelo de aprendizaje automático.

En ambos casos, el entrenamiento ocurre usando ejemplos. De manera similar a cómo se le enseña a un niño a identificar una manzana, a un modelo de aprendizaje automático se le puede enseñar cómo identificar una manzana en una imagen al proporcionar varias imágenes que contienen una manzana.

A partir de estas imágenes de ejemplo, el modelo aprende las características de una manzana, como su forma y color. Ahora, cuando se presenta una nueva imagen de una manzana a esta computadora con este modelo, puede usar lo que había aprendido antes sobre las manzanas e identificar que esta nueva imagen también contiene una manzana.

### Cómo enseñamos a las computadoras a entender imágenes
[En esta increíble charla TED] (https://www.youtube.com/watch?v=40riCqvRoMs), Fei Fei Li, codirectora del Instituto Stanford para la inteligencia artificial centrada en el ser humano, habla sobre el [conjunto de datos de ImageNet ](https://image-net.org/): un gran conjunto de datos de más de 14 millones de imágenes, diseñado por académicos destinados a la investigación de visión por computadora que ella creó con otros investigadores.

El video se remonta a hace 5 años, pero sigue siendo relevante hoy en día. ImageNet ha jugado un papel importante en el avance de la visión artificial. Es útil para muchas aplicaciones de visión artificial y es uno de los conjuntos de datos más populares para visión artificial hasta la fecha.

También habla sobre las redes neuronales convolucionales y su papel crucial en este dominio. Pronto aprenderemos más sobre CNN a través de una sesión grabada.

## Visión por computador

La visión por computadora, a menudo abreviada como CV (Computer Vision), es un campo de inteligencia artificial que entrena a las computadoras para interpretar y comprender el mundo visual.

Desglosándolo en el significado de las palabras que la constituyen, Computer Vision = dar visión a las computadoras.

Usando imágenes digitales de cámaras y videos y modelos de aprendizaje profundo, las máquinas pueden identificar y clasificar objetos con precisión, y luego reaccionar a lo que "ven".

Computer Vision es solo una de las muchas aplicaciones de Deep Learning.

El objetivo de la visión artificial es comprender el contenido de las imágenes digitales. Por lo general, esto implica el desarrollo de métodos que intentan reproducir la capacidad de la visión humana.

### Cómo ML y DL revolucionaron la visión artificial
El aprendizaje automático ayudó a resolver muchos problemas desafiantes para las herramientas y enfoques clásicos de desarrollo de software. Por ejemplo, hace años, los ingenieros de aprendizaje automático pudieron crear un software que podía predecir las ventanas de supervivencia del cáncer de mama mejor que los expertos humanos. Sin embargo, desarrollar las características del software requirió el esfuerzo de docenas de ingenieros y expertos en cáncer de mama y llevó mucho tiempo desarrollarlo.

El aprendizaje profundo proporcionó un enfoque fundamentalmente diferente para realizar el aprendizaje automático. El aprendizaje profundo se basa en redes neuronales, una función de propósito general que puede resolver cualquier problema representable a través de ejemplos. Cuando proporciona a una red neuronal muchos ejemplos etiquetados de un tipo específico de datos, podrá extraer patrones comunes entre esos ejemplos y transformarlos en una ecuación matemática que ayudará a clasificar futuras piezas de información.






![image.png](https://dphi-live.s3.amazonaws.com/media_uploads/image_b9686f5367ce4b8b8e6585b767f2b8d9.png)







_Image source: zbigatron_
### DL - La estrella de Computer Vision
El aprendizaje profundo es un método muy efectivo para hacer visión artificial. En la mayoría de los casos, la creación de un excelente algoritmo de aprendizaje profundo se reduce a recopilar una gran cantidad de datos de entrenamiento etiquetados y ajustar parámetros como el tipo y la cantidad de capas de redes neuronales y épocas de entrenamiento. En comparación con los tipos anteriores de aprendizaje automático, el aprendizaje profundo es más fácil y rápido de desarrollar e implementar.

La mayoría de las aplicaciones actuales de visión por computadora, como la detección de cáncer, los automóviles autónomos y el reconocimiento facial, utilizan el aprendizaje profundo. Gracias a la disponibilidad y los avances en hardware y recursos de computación en la nube, el aprendizaje profundo y las redes neuronales profundas han pasado del ámbito conceptual a las aplicaciones prácticas.

### Aplicaciones de la visión artificial

#### CV en vehículos autónomos

La visión por computadora permite que los autos sin conductor den sentido a su entorno. Las cámaras capturan video desde diferentes ángulos alrededor del automóvil y lo transmiten al software de visión por computadora, que luego procesa las imágenes en tiempo real para encontrar los extremos de las carreteras, leer las señales de tráfico y detectar otros automóviles, objetos y peatones. El automóvil autónomo puede luego conducir su camino en calles y autopistas, evitar chocar con obstáculos y (con suerte) conducir de manera segura a sus pasajeros a su destino.




![imagen.png](https://dphi-live.s3.amazonaws.com/media_uploads/image_1b5683c870c644739a86e6456a05efb5.png)







#### CV en reconocimiento facial

La visión por computadora también juega un papel importante en las aplicaciones de reconocimiento facial, lo que permite a las computadoras hacer coincidir las imágenes de los rostros de las personas con sus identidades. Los algoritmos de visión artificial detectan rasgos faciales en imágenes y los comparan con bases de datos de perfiles faciales. Los dispositivos de consumo utilizan el reconocimiento facial para autenticar las identidades de sus propietarios. Las aplicaciones de redes sociales utilizan el reconocimiento facial para detectar y etiquetar a los usuarios. Los organismos encargados de hacer cumplir la ley también confían en la tecnología de reconocimiento facial para identificar a los delincuentes en las transmisiones de video.





![imagen.png](https://dphi-live.s3.amazonaws.com/media_uploads/image_e154582e549d45c59bbf0485fa3fb2b0.png)





#### CV en Salud

La visión por computadora también ha sido una parte importante de los avances en tecnología de la salud. Los algoritmos de visión artificial pueden ayudar a automatizar tareas como la detección de lunares cancerosos en imágenes de la piel o la detección de síntomas en radiografías y resonancias magnéticas.








![imagen.png](https://dphi-live.s3.amazonaws.com/media_uploads/image_5fed22bbb72240789b7f676307bec988.png)










### Tareas de visión artificial