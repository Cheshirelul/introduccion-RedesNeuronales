
# ¿Qué es una red neuronal?

*Las RNA son sistemas de procesamiento de la información cuya estructura y funcionamiento están inspirados en las redes neuronales biológicas.* (Hilera y Martínez, 1995).

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
- 