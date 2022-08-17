## Objetivos de aprendizaje

* Red adversaria generativa (GAN)
* Autoencoders (Auto codificadores)
* Redes Neuronales como Aproximadores Universales
* Red neuronal recurrente (RNN)
* Memoria a corto plazo (LSTM)
* Unidad Recurrente Cerrada (GRU)


## Redes Neuronales como Aproximadores de Valor Universal

¡Uno de los hechos más sorprendentes sobre las redes neuronales es que pueden calcular cualquier función!

Las redes neuronales tienen una especie de universalidad. No importa qué función queramos calcular, sabemos que hay una red neuronal que puede hacer el trabajo. Por eso se les conoce como Aproximadores de Valor Universal.

Si estas interesado en obtener más información al respecto, este artículo brinda una explicación simple y principalmente visual del teorema de universalidad:

http://neuralnetworksanddeeplearning.com/chap4.html

Hasta ahora, has trabajado con MLP y CNN, que te introdujeron en Deep Learning.

Pero, ¿qué más hay por ahí? ¡Echemos un vistazo!


## Red neuronal recurrente

Imagina que estás viendo una película. Lo más probable es que puedas conectarte a las escenas de la película y entender lo que está pasando, ¿verdad? Todo nuestro pensamiento fluye y podemos conectarnos fácilmente al cuadro actual en función del cuadro anterior. Nuestros pensamientos tienen persistencia.

Bueno, ¿podemos esperar que una red neuronal le dé sentido? ¡Realmente no!

Nuestras arquitecturas de redes neuronales tradicionales (redes neuronales de avance) no pueden hacer esto. Dada una secuencia particular de cuadros, no pueden predecir o comprender lo que sucede en cada punto de la película.

No tienen memoria de la entrada que reciben y son malos para predecir lo que vendrá después. Debido a que una red de retroalimentación solo considera la entrada actual, no comprende la secuencia o el tiempo. Simplemente no puede recordar nada sobre eventos pasados ​​excepto su entrenamiento.




![imagen.png](https://dphi-live.s3.amazonaws.com/media_uploads/image_f1f5a2c614a34e5c88c8e59dd283b345.png)






Aquí es donde entra RNN.

En un RNN, la información circula a través de un bucle. Cuando toma una decisión, considera la entrada actual y también lo que ha aprendido de las entradas que recibió anteriormente.






![imagen.png](https://dphi-live.s3.amazonaws.com/media_uploads/image_e09e705a744c42cc8de229b5b737440f.png)






A continuación se muestra una comparación de una red neuronal de alimentación directa (MLP) regular y una red neuronal recurrente (RNN). Podemos ver que RNN sigue un bucle y aprende de las entradas actuales y anteriores.



![imagen.png](https://dphi-live.s3.amazonaws.com/media_uploads/image_cd688a706c6e47faba470e1eb7f86905.png)







### Aplicaciones de RNN

**Clasificación de Sentimientos**: Esta puede ser una tarea de simplemente clasificar tweets en sentimientos positivos y negativos. Entonces, aquí, la entrada sería un tweet de diferentes longitudes, mientras que la salida es de un tipo y tamaño fijos.


![imagen.png](https://dphi-live.s3.amazonaws.com/media_uploads/image_e86f99ccbd2f4a648b146200b0cbba1d.png)


**Traducción de idiomas**: imagina que queremos traducir texto de un idioma (inglés) a otro idioma (francés). Cada idioma tiene su semántica y tendría diferentes longitudes para la misma oración. Entonces, aquí, las entradas, así como las salidas, son de diferentes tamaños.





![imagen.png](https://dphi-live.s3.amazonaws.com/media_uploads/image_f97b044a50634fba9d74534dac875d6f.png)








**Subtítulos de imagen**: aquí, supongamos que tenemos una imagen para la que necesitamos una descripción textual. Entonces tenemos una sola entrada: la imagen y una serie o secuencia de palabras como salida. Aquí, la imagen puede tener un tamaño fijo, pero el resultado es una descripción de diferentes longitudes.








![imagen.png](https://dphi-live.s3.amazonaws.com/media_uploads/image_a029389cac764a88b5b817b9ef90d780.png)









**SketchRNN**

https://magenta.tensorflow.org/assets/sketch_rnn_demo/index.html

Esta aplicación aprende a completar dibujos. Es muy divertido jugar con él. ¡Pruébalo!


No necesita hacer mucho aquí; simplemente coloque un punto o agregue una línea, ¡y la aplicación hará el resto!



![imagen.png](https://dphi-live.s3.amazonaws.com/media_uploads/image_b98928ee8d8b462bba8a6ebf6b5bf756.png)



### Problemas con RNN estándar

* Problemas de desaparición numérica del gradiente
* Problemas de explosión numérica del gradiente
* Entrenar a un RNN es una tarea comparativamente difícil a otras.
* No puede procesar secuencias muy largas utilizando tanh o relu como función de activación.

## Memoria a corto plazo (LSTM)
* Las redes de memoria a corto plazo (LSTM) son una versión modificada de las redes neuronales recurrentes (RNN) que facilitan el recuerdo de datos pasados ​​en la memoria.
* El problema de la desaparición numérica del gradiente de RNN se resuelve aquí.
* Advertencia: la siguiente imagen puede parecer demasiado compleja en este momento. No hay nada que temer; Aprenderás esto en el próximo bootcamp.






![imagen.png](https://dphi-live.s3.amazonaws.com/media_uploads/image_00e9b01fdc2a495690bcd1e7ff32d31f.png)







## Unidad recurrente cerrada (GRU)
* GRU (Unidad recurrente cerrada) tiene como objetivo resolver el problema de la desaparición numérica del gradiente, que viene con una red neuronal recurrente estándar.
* GRU también se puede considerar como una variación del LSTM porque ambos están diseñados de manera similar y, en algunos casos, producen resultados igualmente excelentes.
* ¡Otra alerta de imagen de aspecto complejo! Un recordatorio amable: se vuelve más fácil cuando lo entiendes completamente.









![imagen.png](https://dphi-live.s3.amazonaws.com/media_uploads/image_2380a37ba4f547ed8e84101075134af0.png)








## Red adversaria generativa (GAN)
Vaya a https://thispersondoesnotexist.com/

¿Que ves? Un ser humano promedio, ¿verdad?

Si no lo averiguó por el nombre del sitio web, ¡la persona que vio no existe! Es una imagen generada por una técnica de Deep Learning llamada GAN. Verás una persona completamente nueva cuando actualices el sitio web. ¿Cuan genial es eso?






![imagen.png](https://dphi-live.s3.amazonaws.com/media_uploads/image_c8c054c7a6eb45faa3a8779728005401.png)






Veamos algunos ejemplos para entender de qué son capaces una GAN y sus variantes:



![imagen.png](https://dphi-live.s3.amazonaws.com/media_uploads/image_c605b62e49e7442b9372d3972d2a2d74.png)



* Dada una imagen de la carretera, la red puede rellenar los detalles con objetos como coches, etc.
* La red puede convertir una imagen en blanco y negro en una imagen en color.
* Dado un mapa aéreo, la red puede encontrar las carreteras en la imagen.
* También puede rellenar los detalles de una foto, teniendo en cuenta los bordes.

La red aprende a generar a partir de una distribución de entrenamiento a través de un juego de 2 jugadores. Las dos entidades son Generador y Discriminador.





![imagen.png](https://dphi-live.s3.amazonaws.com/media_uploads/image_0ae902212e084e4e9d205958a77909d4.png)




Como puede identificar por sus nombres, se usa un generador para generar imágenes que parecen reales, y el trabajo del discriminador es determinar cuál es falso. No hay necesidad de entrar en sus detalles en este momento. ¡Simplemente disfruta de la gloria de las GAN!

## DeepFakes

DeepFakes crea engaños convincentes de imágenes, audio y video.










<iframe width="560" height="315" src="https://www.youtube.com/embed/cQ54GDm1eL0" title="Reproductor de video de YouTube" frameborder="0" allow="acelerómetro; reproducción automática; portapapeles- escribir; medios cifrados; giroscopio; imagen en imagen" allowfullscreen></iframe>









Sí, el expresidente estadounidense Barack Obama no dijo las cosas en el video anterior.

Érase una vez, los investigadores estaban interesados ​​​​en crear DeepFakes.

Ahora, ¡están trabajando para detectarlos!

## Codificadores automáticos
* Autoencoder aprende a comprimir y codificar datos de manera eficiente, luego aprende a reconstruir los datos.
* Reduce las dimensiones de los datos al aprender a ignorar el ruido en los datos.




![imagen.png](https://dphi-live.s3.amazonaws.com/media_uploads/image_969569dc5aa94a24b7fadcbe71dfbb40.png)




### Aplicaciones de los Autoencoders


* Reducción de dimensionalidad
* Compresión de imagen
* Eliminación de ruido de imagen
* Extracción de características
* Generación de imágenes
* Predicción de secuencia a secuencia
* Sistema de recomendación

### Material Adicional (Opcional)

* Una introducción muy básica a la implementación de una Red Neuronal Recurrente:
https://pythonprogramming.net/recurrent-neural-network-deep-learning-python-tensorflow-keras/
* Implementación de GAN en Tensorflow 2.0: https://towardsdatascience.com/demystifying-gans-in-tensorflow-2-0-9890834ab3d9
* Codificador automático con Tensorflow 2.0:
https://www.geeksforgeeks.org/ml-autoencoder-with-tensorflow-2-0/

Eso es solo la punta del iceberg. Hay muchas más redes neuronales por ahí!

Por nombrar algunos más:
* Máquina Boltzmann
* LSTM bidireccionales
* Redes de creencias profundas
* Redes Neuronales de Función de Base Radial

No, no es necesario sumergirse en todos ellos ahora. Repase los que hemos explicado anteriormente; si encuentra algunos de ellos interesantes, lea sobre ellos e intente implementarlos.

Si no, sigue perfeccionando tus habilidades para construir modelos MLP y CNN. Cubriremos temas avanzados de Deep Learning como los mencionados anteriormente en las diapositivas en un futuro Deep Learning Bootcamp.

Estén atentos para saber cuándo sucede eso :)

### Enlace de descarga de diapositivas
Puede descargar las diapositivas de este módulo [aquí](https://docs.google.com/presentation/d/1ZGrz6v_L7WDLf6onRw1S2SQQGSqhk8dy9bAuVJuZX9A/edit?usp=sharing).

### Referencias
* https://www.analyticsvidhya.com/blog/2017/12/introduction-to-recurrent-neural-networks/
* https://builtin.com/data-science/recurrent-neural-networks-and-lstm
* https://towardsdatascience.com/generative-adversarial-networks-explained-34472718707a