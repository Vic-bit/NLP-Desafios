# NPL-Desafíos

En este repositorio se encuentran los desafíos de la cátedra Procesamiento del Lenguaje Natural de la carrera de Especialización en Inteligencia Artificial de la Universidad de Buenos Aires.

## Desafío 1

**1**. Vectorizar documentos. Tomar 5 documentos al azar y medir similaridad con el resto de los documentos. Estudiar los 5 documentos más similares de cada uno analizar si tiene sentido la similaridad según el contenido del texto y la etiqueta de clasificación.

![image](https://github.com/user-attachments/assets/83d854b5-99ec-4fc4-8bac-75cf4cd934ea)

**2**. Entrenar modelos de clasificación Naïve Bayes para maximizar el desempeño de clasificación(f1-score macro) en el conjunto de datos de test. Considerar cambiar parámetros de instanciación del vectorizador y los modelos y probar modelos de Naïve Bayes Multinomial y ComplementNB.

<img width="598" alt="image" src="https://github.com/user-attachments/assets/92cb8c77-4e00-410b-89c7-1705c1ace41c">

![image](https://github.com/user-attachments/assets/9f9feb8e-c3bc-4482-81ca-7ceaffd55d30)

**3**. Transponer la matriz documento-término. De esa manera se obtiene una matriz término-documento que puede ser interpretada como una colección de vectorización de palabras. Estudiar ahora similaridad entre palabras tomando 5 palabras y estudiando sus 5 más similares.

<img width="284" alt="image" src="https://github.com/user-attachments/assets/e564e66f-f364-4d82-b507-beb794a2d0cc">


## Desafío 2

Crear sus propios vectores con Gensim basado en lo visto en clase con otro dataset.

Probar términos de interés y explicar similitudes en el espacio de embeddings.

Intentar plantear y probar tests de analogías. Graficar los embeddings resultantes.

Sacar conclusiones.

Se usa como corpus las letras de algunas canciones del primer y segundo álbum de Linkin Park (Hybrid Theory y Meteora). Este corpus ser realizó a mano.

Se buscaron las 10 palabras que más se relacionaban con "crawling" seindo estas:

<img width="271" alt="image" src="https://github.com/user-attachments/assets/6a60a3eb-0e53-4719-9231-6f7df2184c50">

Se visualiza la agrupación de los vectores donde en este caso se ven los términos que forman parte del estribillo de la canción In the End.
<img width="937" alt="image" src="https://github.com/user-attachments/assets/dc57a075-380d-4554-9d17-71c20b248cd9">

También se pueden visualizar en 3d.
<img width="866" alt="image" src="https://github.com/user-attachments/assets/6b3f603f-5b61-42e3-bcb9-b1fd2d92191c">



## Desafío 3

Se dividió el desafío en 2 partes, una usando un modelo de lenguaje con tokenización por palabras y otra por caracteres.

### Modelo de lenguaje con tokenización por palabras

#### Consigna
- Seleccionar un corpus de texto sobre el cual entrenar el modelo de lenguaje.
- Realizar el pre-procesamiento adecuado para tokenizar el corpus, estructurar el dataset y separar entre datos de entrenamiento y validación.
- Proponer arquitecturas de redes neuronales basadas en unidades recurrentes para implementar un modelo de lenguaje.
- Con el o los modelos que consideren adecuados, generar nuevas secuencias a partir de secuencias de contexto con las estrategias de greedy search y beam search determístico y estocástico. En este último caso observar el efecto de la temperatura en la generación de secuencias.

- #### Sugerencias
- Durante el entrenamiento, guiarse por el descenso de la perplejidad en los datos de validación para finalizar el entrenamiento. Para ello se provee un callback.
- Explorar utilizar SimpleRNN (celda de Elman), LSTM y GRU.
- rmsprop es el optimizador recomendado para la buena convergencia. No obstante se pueden explorar otros.

Se usó como dataset la letra de todas las canciones de Linkin Park.

Se entrenaron varios modelos dando el mejor de estos usando capas GRU Bidirecionales, donde se obtuvo el menor valor de perplejidad y loss:
<img width="563" alt="image" src="https://github.com/user-attachments/assets/f2ff3f8c-47f5-4283-b7c7-bf5d737d4ca4">

Se probó generar una secuencia, la letra de una canción 'I wanna run away and open up my' y completó correctamente con la palabra 'mind'.

También se usó Beamsearch y muestreo aleatorio, para la misma secuencia a compeltar pero esta vez con un término menos, 'I wanna run away and open up', dieron los siguente 5 resultados:
<img width="316" alt="image" src="https://github.com/user-attachments/assets/e35520d8-7f17-4d3e-82d8-5e34a899f434">

### Modelo de lenguaje con tokenización por caracteres

Utilizaremos como dataset una historia de Magic The Gathering, llamada Family Values.
<img width="533" alt="image" src="https://github.com/user-attachments/assets/05e8b635-7c57-45b0-b21c-b7142d9d8bba">


## Desafío 4
El objecto es utilizar datos disponibles del challenge ConvAI2 (Conversational Intelligence Challenge 2) de conversaciones en inglés. Se construirá un BOT para responder a preguntas del usuario (QA)

El modelo completo (encoder+decoder) para poder entrenar es:
![image](https://github.com/user-attachments/assets/f1360b92-6c63-4aad-8305-0113e2a8276b)

Al entrenar la curva de accuracy para train y loss fue la siguiente:
<img width="405" alt="image" src="https://github.com/user-attachments/assets/82ef88f0-b834-471c-b96e-857218d86546">

Las inferencias obtenidas con el modelo entrenado fueron las siguientes:
<img width="310" alt="image" src="https://github.com/user-attachments/assets/7f113dff-e49b-43b8-98fc-60beb1538a79">
<img width="289" alt="image" src="https://github.com/user-attachments/assets/b2ee9935-8d9b-4943-ba62-747f9a5207b7">
<img width="269" alt="image" src="https://github.com/user-attachments/assets/826bb428-88a4-4b1f-ab5f-965fcf449065">
<img width="261" alt="image" src="https://github.com/user-attachments/assets/ae3fb8b4-143a-448b-a5e0-bbc57500f9e3">
<img width="241" alt="image" src="https://github.com/user-attachments/assets/d8859e61-cb06-44ab-80a0-30846b182bbf">

## Desafío 5




