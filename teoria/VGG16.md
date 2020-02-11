# VGG16

VGG16 es un modelo de red neuronal convolucional propuesto por K. Simonyan y A. Zisserman de la Universidad de Oxford en el documento “Very Deep Convolutional Networks for Large-Scale Image Recognition”.

<img src="vgg16-neural-network.jpg">

La entrada a la capa cov1 es de imagen RGB de tamaño fijo 224 x 224. La imagen se pasa a través de una pila de capas convolucionales (conv.), Donde los filtros se usaron con un campo receptivo muy pequeño: 3 × 3 (que es el tamaño más pequeño para capturar la noción de izquierda / derecha, arriba / abajo, centro) ) En una de las configuraciones, también utiliza filtros de convolución 1 × 1, que pueden verse como una transformación lineal de los canales de entrada (seguida de no linealidad). La zancada de convolución se fija a 1 píxel; el acolchado espacial de conv. La entrada de capa es tal que la resolución espacial se conserva después de la convolución, es decir, el relleno es de 1 píxel para 3 × 3 conv. capas. La agrupación espacial se lleva a cabo mediante cinco capas de agrupación máxima, que siguen algunas de las conv. capas (no todas las capas de conv. van seguidas de una agrupación máxima). La agrupación máxima se realiza en una ventana de 2 × 2 píxeles, con zancada 2.

Tres capas totalmente conectadas (FC) siguen una pila de capas convolucionales (que tiene una profundidad diferente en diferentes arquitecturas): las dos primeras tienen 4096 canales cada una, la tercera realiza la clasificación ILSVRC de 1000 vías y por lo tanto contiene 1000 canales (uno para cada clase). La capa final es la capa soft-max. La configuración de las capas completamente conectadas es la misma en todas las redes.

Todas las capas ocultas están equipadas con la no linealidad de rectificación (ReLU). También se observa que ninguna de las redes (excepto una) contiene Normalización de respuesta local (LRN), tal normalización no mejora el rendimiento en el conjunto de datos ILSVRC, pero conduce a un mayor consumo de memoria y tiempo de cálculo.
