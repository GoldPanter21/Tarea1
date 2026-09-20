# Evolución de los modelos

[Volver al README principal](../README.md)

## Modelo de Lenguaje (LM):
Los LM son pilares de los sistemas de procesamiento de lenguaje natural. Son algoritmos que en general "entienden" y "analizan" el lenguaje humano y basicamente son la base de que las IA´s actuales sean tan útiles cómo lo son actualmente, ya que gracias a estos modelos, se puede "conversar" con estas inteligancias o redes.

Un Modelo de Lenguaje es una probabilidad de distribución sobre las secuencias de palabras.<br>
Se usa en el procesamiento de lenguaje natural para predecir la secuencia de palabras que seguirá el lenguaje. Suelen entrenarse en "text corpora", en uno o varios lenguajes con la finalidad de entrenar las diferentes posibles cadenas de texto existentes y finalmente, después de haber sido entrenado, se puede usar para gener nuevas cadenas de texto. <br>
En otras palabras un modelo de lenguaje es una IA que puede entender y generar nuevo texto 

## Modelo de Lenguaje Grande (LLM):
Son tipicamente entrenados con cantidades de texto a nivel industrial, para tomar de ejemplo, podemos tomar colecciones enteras de libros, articulos u otros materiales escritos.<br>
Usan algoritmos sofisticados y redes neuronales con la finalidad de aprender patrones y estructuras del lenguaje permitiendo que generen respuestas coherentes e interesantes ante una gran variedad de instrucciones(prompts) y busquedas estructuradas (queries).<br>
A estos modelos también se les conoce cómo modelos de IA´s Generativas que son herramientas muy poderosas de generación de texto, sin embargo, es importante verificar la información generada ya que puede cometer errores o dar información falsa debido a la información con la que fué entrenada. 

## ¿Cómo se pasa de un LM a un LLM?
Inicialmente un LM se basaba en con una conversación inicial, intentar predecir la siguiente palabra (cómo el autocorrector del telefono). Se manejó así hasta que llegó la arquitectura de Red Neuronal "Transformer" que nos brindó mecanismos de atención, que lograba hacer que se evaluen la importancia de las palabras en una secuencia y así dar sentido a una cadena más larga.<br>
Finalmente para pasar de LM a un LLM se entrenó esta arquitectura sobre enormes cadenas de texto mediante un aprendizaje semi o autosupervisado. Lo que le permitió al modelo sin interferencia de etiquetas humanas.<br>
Las principales diferencias entre el LM y el LLM son: 
- Cantidad de Parámetros: El recuento de parámetros de un LLM es por mucho superior al de un LM.
- Predicción vs Razonamiento: Un LM está diseñado para predecir la palabra más probable siguiente en el texto, un LLM esta entrenado para razonar el texto y generar texto coherente.
- Capacidad de Genración: Un LM está diseñado para generar un poco de texto a lo sumo, en comparación, los LLM ya están diseñados para manejar texto, imágenes, audio y videos (Actualmente, hasta gestionar herramientas con mínima intervención humana).

## Modelo de Razonamiento Explícito: 
Previo a explicar un razonamiento explícito, debemos hablar de la escalabilidad de interferencia, que se basa en la capacidad de un sistema para agrandarse sin aumentar interferencias (ya que donde se causa interferencia, se aplican mejoras).<br>
Es importante aclarar, que debido a la diferenncia anterior entre LM y LLM es unicamente el aumento de parámetros y una mayor cantidad de texto, pero no es en su totalidad cierto. Ya que si no, lo único que se tendría que hacer para mejorar, sería aumentarlos, pero llega un momento en el que más no significa mejor. Aquí es donde entra la escalabilidad por interferencia y para aplicarla se requiere que el LM analice lo que está poniendo y encuentre errores en su razonamiento, por lo que no se ocupa que el automata genere texto más rápido, si no que pula esas respuestas. <br>
Un modelo de razonamiento explicito es un modelo que entrena mediante penalizaciones y recompensas las resspuestas, ya no es solo generar texto congruente, es generar texto que se mejore a si mismo para tener mayor fiabilidad. De esta forma, un LLM ya no solo genera un posible camino, si no que genera muchos caminos en sus respuestas y va puliendo hasta generar una respuesta mucho mejor. También, este enfoque permite no tener que contar con tantos parámetros de entrenamineto y aún así llegar a soluciones viables y entenibles.

## Bibliografía:
- FutureBeeAI, “What is a Language Model: Introduction, Use Cases,” FutureBeeAI, Jun. 09, 2025. https://www.futurebeeai.com/blog/what-is-a-language-model
- “History of LLMS: Complete Timeline & Evolution (1950-2026),” Feb. 19, 2026. https://toloka.ai/blog/history-of-llms/
- L. Lastras, “Reasoning in Granite 3.2 using inference scaling,” IBM Research, Feb. 26, 2025. https://research.ibm.com/blog/inference-scaling-reasoning-ai-model