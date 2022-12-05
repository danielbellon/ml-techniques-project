# Machine Learning Techniques (Proyecto Final)

<!-- TABLE OF HEADER -->
[![Python][skill-python-shield]][skill-python-url]
[![Jupyter][skill-jupyter-shield]][skill-jupyter-url]
[![Tensorflow][skill-tensorflow-shield]][skill-tensorflow-url]
[![Keras][skill-keras-shield]][skill-keras-url]
[![Keras][skill-scikit-learn-shield]][skill-scikit-learn-url]


<!-- TOC -->

* [Machine Learning Techniques (Proyecto Final)](#machine-learning-techniques--proyecto-final-)
    * [Acerca del proyecto](#acerca-del-proyecto)
    * [Organización del Proyecto](#organización-del-proyecto)
    * [Pre-requisitos](#pre-requisitos)
    * [Construyendo el dataset](#construyendo-el-dataset)
    * [Entrenando el modelo](#entrenando-el-modelo)
    * [Usando el modelo](#usando-el-modelo)
    * [Demo](#demo)

<!-- TOC -->

<!-- ABOUT THE PROJECT -->

## Acerca del proyecto

La detección de objetos es uno de los problemas más complejos del área de visión por computador, esto se debe a que los
modelos deben realizar varias tareas a la misma vez, como encontrar diferentes instancias de un objeto en la imagen,
localizar cada objeto por medio de una bounding-box (coordenadas de un rectángulo que rodea al objeto), y clasificarlo
correctamente entre diferentes clases.
El objetivo de este estudio será plantear modelos que se centren en la fase inicial del problema de detección de
objetos, es decir, que sean modelos con la capacidad de localizar y clasificar correctamente una única instancia por
imagen.
Con este fin se construyen diferentes modelos dentro de los cuales el de mejor desempeño consta del uso del modelo VGG19
como base para extraer los feature-maps relevantes de las imágenes, y a partir del cual se crean 2 ramas de capas densas
con dos objetivos diferentes que son la clasificación y localización del dígito. Modelo con el cual se obtiene un 72.37%
de accuracy en la clasificación.

## Organización del Proyecto

> ⚠️ Antes de clonar el proyecto es importante tener instalado [Git LFS](https://git-lfs.github.com/), asegúrese de
> haber
> ejecutado `git lfs install`

```bash
$ git clone git@github.com:danielbellon/ml-techniques-project.git
``` 

Para descargar el proyecto en su equipo lo puede hacer por medio del siguiente comando que clona el proyecto en git.
Como resultado deberá obtener la siguiente estructura de carpeta.

    ├── annotations                         <- Etiquetas de cada uno de los datasets
    │   ├── extraDigitStruct.json           
    │   ├── testDigitStruct.json                            
    │   └── trainDigitStruct.json           
    ├── .gitattributes
    ├── .gitignore                          
    ├── exported_model.h5                   <- Modelo exportado
    ├── pre_process_data.ipynb              <- Notebook para la construcción del dataset
    ├── ptmodel7_1digit_with_bbox.ipynb     <- Notebook con el proceso de entrenamiento del mejor modelo obtenido
    └── readme.md                           

## Pre-requisitos para Google Colab

El proyecto tiene ciertas precondiciones que tienen que satisfacerse si el entorno de ejecución es **Google Colab**. En el
archivo `requirements.txt`
se encuentran aquellas librerías que tienen que instalarse en el ambiente, y pueden ser instaladas ejecutando
el siguiente comando en la raíz del proyecto:

``` bash
$ pip install -r requirements.txt
```

## Construyendo el dataset

Inicialmente, el proyecto requiere de hacer un preprocesamiento de los datos para obtener un dataset óptimo para
entrenar
el modelo. Para esto nos podemos apoyar ejecutando el notebook [pre_process_data.ipynb](pre_process_data.ipynb)
obteniendo como resultado los siguientes archivos:

    ├── preprocessed_train                  <- Carpeta con los vectores de entrenamiento
    │   ├── Xtrain.npy                      
    │   ├── labels.npy                                       
    │   ├── bboxes.npy                                       
    │   └── imagePaths.npy                  
    ├── preprocessed_test                   <- Carpeta con los vectores de prueba
    │   ├── Xtrain.npy                      
    │   ├── labels.npy                                       
    │   ├── bboxes.npy                                       
    │   └── imagePaths.npy                  

## Entrenando el modelo

Para realizar el entrenamiento se debe usar el notebook [ptmodel7_1digit_with_bbox.ipynb](ptmodel7_1digit_with_bbox.ipynb)
obteniendo como resultado los siguientes archivos:

    ├── models                              <- Carpeta con los modelos entrenados
    │   ├── ptmodel7_1digit_with_bbox
    |   |   ├── best_model_ft.hdf5
    |   |   ├── model.h5
    |   |   ├── model_ft.h5
    |   |   ├── model_ft_history.npy
    |   |   ├── model_history.npy
    |   |   └── plots
    |   |       ├── accs.png
    |   |       ├── confusion_matrix.png
    |   |       ├── ft_accs.png
    |   |       ├── ft_losses.png
    |   |       └── losses.png

## Usando el modelo

Para poder utilizar el modelo, se construyó una interfaz gráfica de usuario con **Gradio**, y dicha UI se montó en un 
espacio de **Hugging Face** al que se puede acceder mediante el siguiente enlace: 
https://huggingface.co/spaces/danielbellon/ml-techniques-project

El código de la demostración también está alojado en **Hugging Face** (https://huggingface.co/spaces/danielbellon/ml-techniques-project/tree/main)

<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://shields.io/ -->
[skill-python-shield]: https://img.shields.io/badge/Python-3.9-blue
[skill-python-url]: https://www.python.org/
[skill-jupyter-shield]: https://img.shields.io/badge/Jupyter-6.4.8-blue
[skill-jupyter-url]: https://jupyter.org/
[skill-tensorflow-shield]: https://img.shields.io/badge/TensorFlow-2.9.1-blue
[skill-tensorflow-url]: https://www.tensorflow.org/?hl=es-419
[skill-keras-shield]: https://img.shields.io/badge/Keras-2.9.0-blue
[skill-keras-url]: https://keras.io/getting_started/
[skill-scikit-learn-shield]: https://img.shields.io/badge/SciKit_Learn-1.1.3-blue
[skill-scikit-learn-url]: https://scikit-learn.org/stable/install.html
