
# ¿Qué es una red neuronal?

*Las RNA son sistemas de procesamiento de la información cuya estructura y funcionamiento están inspirados en las redes neuronales biológicas.* (Hilera y Martínez, 1995).

## Caracteristicas generales

- Consisten en un gran número de elementos simples de procesamiento llamados nodos o neuronas que están organizados en capas.
- Cada neurona está conectada con otras neuronas mediante enlaces de comunicación, cada uno de los cuales tiene asociado un peso.
- Los pesos representan la información que será usada por la red neuronal para resolver un problema determinado.

Así, las RNA son sistemas adaptativos que aprenden de la experiencia, esto es, aprenden a llevar a cabo ciertas tareas mediante un entrenamiento con ejemplos ilustrativos.
Mediante este entrenamiento o aprendizaje, las RNA crean su propia representación interna del problema, por tal motivo se dice que son autoorganizadas.

- Las RNA son capaces de generalizar de casos anteriores a casos nuevos.
- Esta característica es fundamental ya que permite responder correctamente a informaciones:
  - novedosas
  - distorcionadas o incompletas
- Funcionan en paralelo
  - Muchas neuronas pueden estar trabajando al mismo tiempo

*Biológicamente, se suele aceptar que el conocimiento está más relacionado con las conexiones entre neuronas que con las propias neuronas* (Alkon, 1989;Shepherd, 1990);
es decir, el conocimiento se encuentra distribuido por las sinapsis de la red. De forma análoga, en el caso de las RNA se puede considerar que el conocimiento se encuentra representado en los pesos de las conexiones entre neuronas.
<center><img src="neuronaBiologica.png"></center>



# Regularización con Dropout

## ¿Qué es?

- Tecnica de regularizacion
- Es aplicada sobre modelos
- Propuesta por Srivastava, et al.

## En que consiste?

Durante el entrenamiento se selecciona *neuronas* de manera aleatoria cuando se esta entrenando el modelo y dichas neuronas son ignoradas.

- La activación de las neuronas es temporalmente removida
- Cualquier actualizacion de pesos no son aplicadas a la neurona predecesora
- Otras neuronas tendran que intervenir durante el entramiento, por lo que la red generara nuevo conocimiento.

Esto daria como resultado multiples interpretaciones internas que seran aprendidas por la red. El efecto es que la red se vuelve menos sensible a los pesos específicos de las neuronas. Esto a su vez da como resultado una red que es capaz de una mejor generalización y es menos probable que sobreajuste los datos de entrenamiento.

# Usando Dropout Regularization en Keras

¿Que debemos saber?

- Necesita un porcentaje
  - Este porcentaje sera usado como base para la probabilidad de que una neurona sea descartada.
- No se usa durante la evaluación
  - Esto unicamente afectara al modelo cuando este siendo entrenado.

## Aplicar Dropout en la capa visible.

Este metodo de generalizacion puede ser empleado tanto en las capas ocultas de nuestra red neuronal, como en las neuronas de entrada.
- Para hacer uso de esta tecnica en Keras y aplicarlo en la capa visible, debemos de declararlo justo antes de la primer capa oculta.
- En el paper original sobre Dropout, nos va la recomendación de poner un *kernel_constrain* con un *max_norm* de 3.

## Usando Dropout en capas ocultas.

Al igual que en las neuronas visibles, dropout puede ser empleado en las neuronas de las capas ocultas.

En algunas ocaciones el usar Dropout en capas ocultas podria no representar una mejora, incluso podria tener un rendimiento peor que el modelo original.

# Consejos para usar Dropout

- Usar valores de dropout entre **20%-50%**, como valor inicial al usar dropout en un modelo se recomienda el 20%. Dar valores muy bajos podrian tener une fecto minimo y emplear valores demasiado altos podrian hacer que no aprenda neustra red.
- Usar redes neuronales largas, es probable que se obtenga un mejor rendimiento puesto que da la oportunidad de aprender representaciones independientes a las neuronas que comprenden la red.
- Usar esta tecnica tanto en neuronas ocultas como en las de entrada (visibles). En cada capa la red da buenos resultados.
- Use una gran *tasa de aprendizaje*(learning rate) con decadencia y un gran *momentum*. Aumente su *tasa de aprendizaje* en un factor de 10 a 100 y use un valor de *momentum* alto de 0.9 o 0.99.
- Restringir el tamaño de los *pesos* de la red. Un *learning rate* alto puede dar lugar a *pesos* de red muy grandes. Se ha demostrado que imponer una restricción en el tamaño de los *pesos* de la red, como la regularización de max-norm con un tamaño de 4 o 5, mejora los resultados.