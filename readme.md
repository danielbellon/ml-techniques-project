# Machine Learning Techniques (Proyecto Final)

<!-- TABLE OF HEADER -->
[![Python][skill-java-shield]][skill-java-url]
[![Jupyter][skill-spring-shield]][skill-spring-url]
[![Tensorflow][skill-springdoc-shield]][skill-springdoc-url]
[![Keras][skill-lombok-shield]][skill-lombok-url]


<!-- ABOUT THE PROJECT -->
## Acerca del proyecto

La detección de objetos es uno de los problemas más complejos del área de visión por computador, esto se debe a que los modelos deben realizar varias tareas a la misma vez, como encontrar diferentes instancias de un objeto en la imagen, localizar cada objeto por medio de una bounding-box (coordenadas de un rectángulo que rodea al objeto), y clasificarlo correctamente entre diferentes clases.
El objetivo de este estudio será plantear modelos que se centren en la fase inicial del problema de detección de objetos, es decir, que sean modelos con la capacidad de localizar y clasificar correctamente una única instancia por imagen.
Con este fin se construyen diferentes modelos dentro de los cuales el de mejor desempeño consta del uso del modelo VGG19 como base para extraer los feature-maps relevantes de las imágenes, y a partir del cual se crean 2 ramas de capas densas con dos objetivos diferentes que son la clasificación y localización del dígito. Modelo con el cual se obtiene un 72.37% de accuracy en la clasificación.

## Organización del Proyecto

    ├── annotations                         <- contains the setup and config classes.
    │   ├── extraDigitStruct.json           <- contains the setup and config classes.
    │   ├── testDigitStruct.json            <- contains the setup and config classes.                 
    │   └── trainDigitStruct.json           <- contains the setup and config classes.
    ├── .gitattributes
    ├── .gitignore                          <- contains the implementation of the libraries defined in the settings.gradle
    ├── exported_model.h5                   <- contains the definition and versions of the libraries used by the application.
    ├── demo.ipynb                          <- contains the definition and versions of the libraries used by the application.
    ├── pre_process_data.ipynb              <- contains the definition and versions of the libraries used by the application.
    ├── model.ipynb                         <- contains the definition and versions of the libraries used by the application.
    └── readme.md                           <- The top-level README for developers using this project.

## Construyendo el dataset

## Entrenando el modelo

## Usando el modelo

## Demo

<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://shields.io/ -->
[skill-java-shield]: https://img.shields.io/badge/JAVA-17-blue
[skill-java-url]: https://www.oracle.com/java/technologies/javase/jdk17-archive-downloads.html
[skill-spring-shield]: https://img.shields.io/badge/Spring%20Boot-2.6.3-blue
[skill-springdoc-shield]: https://img.shields.io/badge/SpringDoc-1.6.6-blue
