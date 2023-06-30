# Multispectral image classification using automatic neural network design

## Abstract

In recent times, machine learning has been valued as a powerful tool to drive technological advancement. While the use of this technology and artificial intelligence (AI) in solving global problems and societal concerns has become popular, it is essential to continue working together to establish the most effective way to apply these tools in the battle against climate change.

Juniper (Juniperus communis L.) is one of the most characteristic species in the Sierra Nevada natural park. Consequently, it is one of the species that contributes most to the maintenance of the main workings of the high mountain scrublands. Since they are located  right at the edge of their distribution area, they are very sensitive to small disturbances. A clear example of disturbance in this sense is climate change, which is responsible for long dry periods that do not favor the regeneration of junipers.

Therefore, the objective of this work will be the detection of junipers in the Sierra Nevada region. For this purpose, a set of multiband satellite images, provided and annotated by experts, from different areas of the Sierra Nevada natural park will be used. These images have been captured by WorldView3, a commercial Earth observation satellite. Each image has an associated mask, which indicates where the junipers are located. We found a total of 256 samples, each with two types of associated images: panchromatic and multispectral.

One of the main challenges presented by this project is the lack of powerful architectures to segment images with more than three bands. Therefore, two approaches will be developed. In the first one, the image bands will be reduced to three, in order to use a well-knownnetwork architecture for segmentation tasks, Mask-RCNN. In the second, based on the U-Net architecture, ad-hoc models will be implemented. The purpose of this second approachwill be to build models that can receive all the spectral information of the images, in orderto outperform the first one. Also, due to the low spatial resolution of color images, differentsuper-resolution algorithms (also known as pansharpening in the remote sensing field) will be studied and compared.

## Files description

* Evaluación de modelos adhoc.ipynb: este notebook es el que contiene todo el código referente al post-procesamiento de los resultados. En él se ha implementado el algoritmo de Hill Climbing, el cuál nos permite obtener un ensamblado óptimo con todos los modelos conseguidos en la fase de entrenamiento. 
* Train test split.csv: consiste en un archivo CSV que contiene la partición del conjunto de datos en los conjuntos de entrenamiento, validación y test. 
* Vegetation indexes.py: es el script que almacena todo lo necesario para la implementación del enfoque de Mask-RCNN con los índices de vegetación como método de reducción de la dimensionalidad. El archivo puede dividirse en cuatro secciones. 
    
        1. Preprocesamiento: incluye todos los métodos necesarios para llevar a cabo el preprocesado de las imágenes: pansharpening, data augmentation, etc. 
        2. Modelo y dataset: incluye todo lo necesario para construir el dataset y la clase del modelo en PyTorch. Así mismo, incluye el método de la reducción de dimensionalidad con los índices. 
        3. Entrenamiento: incluye todas las funciones relacionadas con el entrenamiento, validación, métricas, etc. 
        4. Ajuste de hiperparámetros: con todo lo necesario para llevar a cabo el ajuste con la herramienta Weights and Biases. 

* PCA.py: se trata del script usado para la implementación del enfoque de Mask-RCNN con PCA como método de reducción de la dimensionalidad. Presenta una estructura similar al archivo anterior. 
* modelo personalizado.py: consiste en el script usado para la implementación del enfoque ad-hoc. Presenta una estructura similar a los archivos anteriores. 
* Carpeta Multispectral Images: contiene los ficheros y polígonos necesarios para construir las imágenes y sus respectivas máscaras.
