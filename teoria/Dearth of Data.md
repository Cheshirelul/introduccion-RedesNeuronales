# Escasez de datos

Después de realizar todas las técnicas anteriores, si su modelo aún no funciona mejor en su conjunto de datos de prueba, podría atribuirse a la falta de datos de entrenamiento. Hay muchos casos de uso donde la cantidad de datos de capacitación disponibles está restringida. Si no puede recopilar más datos, puede recurrir a técnicas de aumento de datos.

| ![data_augmentation.png](img\data_augmentation.png  "data augmentation") |
|:--:|
| **Data augmentation** from: [data augmentation techniques in cnn using tensorflow](https://medium.com/@prasad.pai/data-augmentation-techniques-in-cnn-using-tensorflow-371ae43d5be9)|

Si está trabajando en un conjunto de datos de imágenes, puede aumentar nuevas imágenes a los datos de entrenamiento al cortar la imagen, voltear la imagen, recortar la imagen al azar, etc. Esto podría proporcionar diferentes ejemplos para que la red neuronal se capacite.
