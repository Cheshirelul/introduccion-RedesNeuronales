# Mejorar el rendimiento de una red neuronal

Las redes neuronales son algoritmos de *machine learning* que proporcionan el estado de la precisión en muchos casos de uso. Sin embargo, muchas veces, la precisión de la red que estamos elaborando puede no ser satisfactoria. Por lo tanto, siempre se tiene que estar buscando mejores formas de mejorar el rendimiento de nuestros modelos. Hay muchas técnicas disponibles que podrían ayudarnos a lograrlo.

## Verificar Overfitting(sobreajuste)



El primer paso para garantizar que nuestra red neuronal funcione bien en los datos de prueba es verificar que la red neuronal no se *sobreajuste*. Bueno,es en esta parte donde es bueno realizarse esta pregunta, ¿qué es el *sobreajuste*(Overfitting)? El *Overfitting (sobreajuste)* ocurre cuando el modelo comienza a **memorizar** valores de los datos de entrenamiento en lugar de **aprender** de ellos. Por lo tanto, cuando el modelo encuentra datos que no ha visto antes, no puede funcionar bien en ellos. 

Para darle una mejor comprensión, repasemos una analogía. Todos tendríamos un compañero de clase que es bueno **memorizando**, y supongamos que se avecina una prueba de matemáticas. Nosotros y nuestro amigo, que es bueno **memorizando**, comenzamos a estudiar del libro de texto. Nuestro amigo continúa memorizando cada fórmula, pregunta y respuesta del libro de texto, pero nosotros, por otro lado, somos ligeramente más inteligentes que él, por lo que decidimos construir sobre la intuición y resolver problemas y **aprender** cómo estas fórmulas entran en juego. Llega el día del examen, si los problemas en el examen se sacan directamente de los libros de texto, entonces como es de esperar nuestro amigo memorizador lo hara mejor, pero si los problemas son nuevos y esto significa que implican aplicar la intuición, a nosotros nos va mejor en el examen y nuestro amigo memorizador falla miserablemente.

## Como identificar si nuestro modelo esta sobreajustado(overfitting)?

<img src="overfitting.png">

Esto se puede verificar haciendo *crosscheck(verificacion cruzada)* con la precisión del entrenamiento y la precisión de las pruebas. Si la precisión del entrenamiento es mucho más alta que la precisión de la prueba, puede postular que su modelo se ha sobreajustado. También puede trazar los puntos predichos en un gráfico para verificar. Existen algunas técnicas para evitar el sobreajuste:

- Regularisation of data (L1 o L2).
- Dropouts: abandonando aleatoriamente de las conexiones entre las neuronas, obligando a la red a encontrar nuevos caminos y generalizar.
- Early Stopping: precipita el entrenamiento de la red neuronal, lo que lleva a una reducción en el error en el conjunto de prueba.
