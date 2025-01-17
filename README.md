# NLP-Desafíos

En este repositorio se encuentran los desafíos de la cátedra Procesamiento Natural del Lenguaje de la Carrera Especialización en Inteligencia Artificial de la Universidad de Buenos Aires.


## Desafío 1

**1**. Se tomaron 5 documentos al azar y se midió la similaridad con el resto. Luego se estudiaron los 5 documentos más similares a cada uno de ellos según el contenido del texto y la etiqueta de clasificación. En la figura se observa que todos los documentos con mayor similaridad tienen la misma etiqueta de clasificación.

<img width="439" alt="image" src="https://github.com/user-attachments/assets/b27a2203-7776-4d9f-b62d-46c614ddbb01">

**2**. Se entrenaron modelos de clasificación Naïve Bayes para maximizar el desempeño de clasificación (f1-score macro) en el conjunto de datos de test. Se probaron diferentes parámetros de instanciación del vectorizador y de los modelos. Se usaron modelos de Naïve Bayes Multinomial y ComplementNB.

<img width="598" alt="image" src="https://github.com/user-attachments/assets/92cb8c77-4e00-410b-89c7-1705c1ace41c">

<img width="599" alt="image" src="https://github.com/user-attachments/assets/d4c205a7-dce7-4776-a321-e0b77765b8f9">

**3**. Se realizó la transpuesta de la matriz documento-término para obtener la matriz término-documento que puede ser interpretada como una colección de vectorización de palabras. Luego se estudió la similaridad entre palabras tomando 5 palabras y estudiando sus 5 más similares como se observa en la siguiente imagen:

<img width="284" alt="image" src="https://github.com/user-attachments/assets/e564e66f-f364-4d82-b507-beb794a2d0cc">


## Desafío 2

Se crearon vectores propios con Gensim basado en un dataset propio formado con los dos primeros álbumes de Linkin Park (Hybrid Theory y Meteora).

Se probaron términos de interés, como por ejemplo "crawling" de la canción Crawling del álbum Hybrid Theory, y se observaron las 10 palabras que más se relacionaban, según el espacio de embeddings, siendo estas:

<img width="271" alt="image" src="https://github.com/user-attachments/assets/6a60a3eb-0e53-4719-9231-6f7df2184c50">

donde se observa que entre ellas se encuentra "skin", lo cual es correcto debido al estribillo de la canción.

Se visualiza la agrupación de los vectores donde en este caso se ven los términos que forman parte del estribillo de la canción In the End.

<img width="937" alt="image" src="https://github.com/user-attachments/assets/dc57a075-380d-4554-9d17-71c20b248cd9">

También se pueden visualizar en 3d.

<img width="866" alt="image" src="https://github.com/user-attachments/assets/6b3f603f-5b61-42e3-bcb9-b1fd2d92191c">

Además se pleantearon tests de analogías como el siguiente con los nombres y apellidos de los vocalistas de la banda, donde se observa a Bennington entre los resultados más similares:

<img width="389" alt="image" src="https://github.com/user-attachments/assets/a69312f5-d32d-41c6-ad28-9b754ff4de76">


## Desafío 3

Se dividió el desafío en 2 partes, una usando un modelo de lenguaje con tokenización por palabras y otra con tokenización por caracteres.

### Modelo de lenguaje con tokenización por palabras

Se usó como dataset uno propio formado por las letras de todas las canciones de Linkin Park. Se lo preprocesó dividiendo el corpus en documentos, siendo estos cada uno de los versos.

Se exploraron diferentes modelos como SimpleRNN, LSTM, GRU, SimpleRNN Bidireccional, LSTM Bidireccional y GRU Bidireccional, donde el último de estos fue el que obtuvo mejores resultados con el menor valor de perplejidad y loss:

<img width="563" alt="image" src="https://github.com/user-attachments/assets/f2ff3f8c-47f5-4283-b7c7-bf5d737d4ca4">

Se probó generar una secuencia, la letra de una canción 'I wanna run away and open up my' y completó correctamente con la palabra 'mind, lo cual es correcto:

<img width="361" alt="image" src="https://github.com/user-attachments/assets/8c6e5fcf-4603-4f39-ad90-1c406fcc33de">


<img width="291" alt="image" src="https://github.com/user-attachments/assets/e5b1e964-e13f-4d11-87b2-d0c6ae12b560">

También se usó Beamsearch y muestreo aleatorio, para la misma secuencia a completar pero esta vez con un término menos, 'I wanna run away and open up', dieron los siguente 5 resultados:

<img width="316" alt="image" src="https://github.com/user-attachments/assets/e35520d8-7f17-4d3e-82d8-5e34a899f434">

### Modelo de lenguaje con tokenización por caracteres

Se utilizó como dataset una historia de Magic The Gathering, llamada Family Values.

Se exploraron diferentes modelos como SimpleRNN, LSTM, GRU, donde el último de estos fue el que obtuvo mejores resultados con el menor valor de perplejidad y loss:

<img width="532" alt="image" src="https://github.com/user-attachments/assets/959357e9-f1a2-4d8f-b209-ef7a70514432">

Utilizando como input en la generación de secuencias el siguiente extracto del corpus: 'Instead, the Grand Envoy of the Orzhov leaned forward,'

Se observa que respondió con algo coherente, sienda la respuesta:

<img width="642" alt="image" src="https://github.com/user-attachments/assets/fc96dd1f-e769-42bc-ac99-67c6320a1a85">


## Desafío 4

El objetivo es utilizar datos disponibles del challenge ConvAI2 (Conversational Intelligence Challenge 2) de conversaciones en inglés. Se construirá un BOT para responder a preguntas del usuario (QA).

Se utilizaron los embeddings de FastText para transformar los tokens de entrada en vectores.

El modelo completo (encoder+decoder) para poder entrenar es:

<img width="811" alt="image" src="https://github.com/user-attachments/assets/e8998b05-99c5-4119-bee2-299ad05343df">


Al entrenar la curva de accuracy para train y loss fue la siguiente:

<img width="551" alt="image" src="https://github.com/user-attachments/assets/5d3a9347-db33-4ac1-9e21-db3a885d1e6a">


Las inferencias obtenidas con el modelo entrenado fueron las siguientes:

<img width="310" alt="image" src="https://github.com/user-attachments/assets/7f113dff-e49b-43b8-98fc-60beb1538a79">


<img width="289" alt="image" src="https://github.com/user-attachments/assets/b2ee9935-8d9b-4943-ba62-747f9a5207b7">


<img width="269" alt="image" src="https://github.com/user-attachments/assets/826bb428-88a4-4b1f-ab5f-965fcf449065">


<img width="261" alt="image" src="https://github.com/user-attachments/assets/ae3fb8b4-143a-448b-a5e0-bbc57500f9e3">


<img width="241" alt="image" src="https://github.com/user-attachments/assets/d8859e61-cb06-44ab-80a0-30846b182bbf">

Se observa que algunas de las inferencias, responden algo coherente. En la primera que se le saluda con "hello", respondiendo con "hello how are you", lo mismo sucede en la segunda que se le pregunta "Hi" y responde con "hello how are you". En el tercer caso se le da como entrada "Tell me about you", respondiendo "i am a girl". En el cuarto caso se le escribe "Be happy" y contesta con "i love to read". Por lo tanto se observa que funciona de manera adecuada, pero tiene el problema de que muchas veces contesta con lo mismo sin importar cual sea la pregunta, como en el caso de preguntas que del tipo "Are you...", donde responde "i am a girl", como se ve en el caso 5.


## Desafío 5

Este último desafío consiste en hacer análisis de sentimiento mediante BERT.

Para ello se va a hacer uso de un dataset que son críticas de Google Apps, donde una de sus columnas son los comentarios de los usuarios.

Se tiene un score que va desde 1 a 5, es decir 5 posibles calificaciones.

Se van a comparar 3 modelos cambiando parte de la arquitectura y de los datos para obervar como varían los resultado.

#### Modelo 1 (base): 3 clases

Se van a condensar los resultados de 1 y 2 en 0, y de 4 y 5 en 2, dejando el score de 3 como 1. De esta manera se convierte la cantidad de clases en 3 siendo estas:

- negative
- neutral
- positive

Al entrenar por 15 épocas se obtienen las siguentes curvas de train y val:

<img width="559" alt="image" src="https://github.com/user-attachments/assets/77eab4d3-d7d0-40cc-9836-bfa80cba0a5e">

La matriz de confusión obtenida fue:

<img width="500" alt="image" src="https://github.com/user-attachments/assets/d512c3c1-f62c-4d75-833b-09af92fbd379">

Se ensaya el modelo con 3 diferentes textos, dando los siguientes resultados:

- text = "I love this app!"
  
<img width="179" alt="image" src="https://github.com/user-attachments/assets/1a80a130-f795-454e-ae6c-f9cf5dc1aa5d">

- text = "It works as expected, but it’s nothing special"
  
<img width="174" alt="image" src="https://github.com/user-attachments/assets/fd10ce7c-0335-4f36-86a5-2ef3295192be">

- text = "I hate this app!"
  
<img width="176" alt="image" src="https://github.com/user-attachments/assets/1660f905-2330-4f14-88e0-cba5b8b52164">


#### Modelo 2: 3 clases, con una capa densa adicional

También se tienen clases en 3 siendo estas:

- negative
- neutral
- positive

Al entrenar por 15 épocas se obtienen las siguentes curvas de train y val:

<img width="554" alt="image" src="https://github.com/user-attachments/assets/ba55263e-4ef1-4cd8-809b-f2562b9ebfe2">

La matriz de confusión obtenida fue:

<img width="501" alt="image" src="https://github.com/user-attachments/assets/6c41ad72-a2ae-43c5-8cc6-13c8f36fbf27">

Se ensaya el modelo con 3 diferentes textos, dando los siguientes resultados:

- text = "I love this app!"
  
<img width="179" alt="image" src="https://github.com/user-attachments/assets/1a80a130-f795-454e-ae6c-f9cf5dc1aa5d">

- text = "It works as expected, but it’s nothing special"
  
<img width="174" alt="image" src="https://github.com/user-attachments/assets/fd10ce7c-0335-4f36-86a5-2ef3295192be">

- text = "I hate this app!"
  
<img width="179" alt="image" src="https://github.com/user-attachments/assets/1a80a130-f795-454e-ae6c-f9cf5dc1aa5d">


#### Modelo 3: 5 clases

No se condensan los valores de score, sino que se representan del 0 al 4, dando un total de 5 clases, siendo estas:

- very negative
- negative
- neutral
- positive
- very positive

Al entrenar por 15 épocas se obtienen las siguentes curvas de train y val:

<img width="551" alt="image" src="https://github.com/user-attachments/assets/167ea51c-dd37-4179-af84-7b8c07849065">

La matriz de confusión obtenida fue:

<img width="501" alt="image" src="https://github.com/user-attachments/assets/123eafc1-f704-4db8-b2da-aba4e3eb9772">

Se ensaya el modelo con 3 diferentes textos, dando los siguientes resultados:

- text = "I love this app!"
  
<img width="220" alt="image" src="https://github.com/user-attachments/assets/d66f0cbf-326b-4dcc-b144-0c1c43a03ee5">


- text = "It works as expected, but it’s nothing special"
  
<img width="181" alt="image" src="https://github.com/user-attachments/assets/e7c6d80e-51ad-42be-bf4b-7ddf6b371f58">

- text = "I hate this app!"
  
<img width="217" alt="image" src="https://github.com/user-attachments/assets/d041b27c-0c66-44f0-a76e-bc4bc1051a0c">

Se puede apreciar que luego de realizar transfer learning con metodología feature extractor, los modelos dieron resultados satisfactorios al evaluarlos. Estos modelos, sobre todo el 2 y el 3 que se ve la curva de validación con un comportamiento inestable, podrían mejorar sus métricas al cambiar algunos hiperparámetros como el learning rate por un valor más pequeño por ejemplo.

A futuro, si se tuviera más poder de cómputo y se usara fine tuning las métricas aumentarían cosiderablemente. 





