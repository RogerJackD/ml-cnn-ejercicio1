Clasificación de Flores con TensorFlow
Este proyecto implementa una red neuronal convolucional (CNN) para clasificar imágenes de flores del dataset Oxford Flowers 102. El modelo se entrena y luego se exporta en diferentes formatos para su uso en diferentes plataformas.

Requisitos
TensorFlow 2.x

TensorFlow Datasets

TensorFlow.js (para la conversión)

Google Colab (opcional, pero usado en este ejemplo)


Exportación del Modelo
El modelo se guarda en 3 formatos:

Keras H5: flowers_model.h5

TensorFlow.js: Carpeta tfjs_model/ comprimida en tfjs_model.zip

SavedModel: Carpeta saved_model/ comprimida en saved_model.zip


Problemas que tuve (y cómo los solucioné)
Error al cargar el dataset

Al principio me daba un error raro cuando intentaba descargar oxford_flowers102.

Solución: Resulta que necesitaba instalar tensorflow-datasets aparte.

El entrenamiento iba MUY lento

La primera vez que lo ejecuté, cada época tardaba una eternidad.

Solución: Me faltaba el .prefetch(buffer_size=tf.data.AUTOTUNE) para optimizar la carga de datos.


Error al guardar el modelo en TF.js

Cuando intentaba convertirlo, a veces fallaba sin razón clara.

Solución: Tuve que asegurarme de que el modelo estuviera bien guardado en .h5 antes de la conversión.

muestra rapida de dataset:
![image](https://github.com/user-attachments/assets/44259291-4777-4a82-9eb4-5a0ae889cb85)


![image](https://github.com/user-attachments/assets/09563b31-062a-4068-8df0-74765115d6c5)
![image](https://github.com/user-attachments/assets/cc258e94-583e-41d8-bee7-6970629a4dcd)


````
GRAFICA DE PRECISION Y PERDIDAS:
````

![image](https://github.com/user-attachments/assets/f6f7dcaa-2065-43b3-af6c-26239b2fb0d9)



test:
![image](https://github.com/user-attachments/assets/fb01583d-8fee-4cfd-96f9-fa1c38602e44)

