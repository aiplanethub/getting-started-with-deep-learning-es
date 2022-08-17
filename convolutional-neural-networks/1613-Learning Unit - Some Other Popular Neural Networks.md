## Objetivos de aprendizaje

* Red adversaria generativa (GAN)
* Autocodificadores
* Redes Neuronales como Aproximadores Universales
* Red neuronal recurrente (RNN)
* Memoria a corto plazo largo (LSTM)
* Unidad Recurrente Cerrada (GRU)


## Redes Neuronales como Aproximadores de Valor Universal

¡Uno de los hechos más sorprendentes sobre las redes neuronales es que pueden calcular cualquier función!

Las redes neuronales tienen una especie de universalidad. No importa qué función queramos calcular, sabemos que hay una red neuronal que puede hacer el trabajo. Por eso se les conoce como Aproximadores de Valor Universal.

Si está interesado en obtener más información al respecto, este artículo brinda una explicación simple y principalmente visual del teorema de universalidad:

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









**BocetoRNN**

https://magenta.tensorflow.org/assets/sketch_rnn_demo/index.html

Esta aplicación aprende a completar dibujos. Es muy divertido jugar con él. ¡Pruébalo!


No necesita hacer mucho aquí; simplemente coloque un punto o agregue una línea, ¡y la aplicación hará el resto!



![imagen.png](https://dphi-live.s3.amazonaws.com/media_uploads/image_b98928ee8d8b462bba8a6ebf6b5bf756.png)