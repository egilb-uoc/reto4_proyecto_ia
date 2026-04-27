# reto4_proyecto_ia
Repositorio para el jpynb del reto 4 del proyecto de IA
Reto 4 - Proyecto IA: Detección de Caídas (SisFall)

Este repositorio contiene la lógica de entrenamiento, validación y exportación de un modelo de Machine Learning (XGBoost) para la detección automática de caídas en personas mayores, utilizando el dataset de SisFall.

Estructura del Repositorio:
processed/: Contiene una muestra de los datos originales (formato CSV) que ya han pasado por la fase de limpieza y preprocesamiento, listos para ser consumidos por el modelo. Son los mismos archivos que están en la carpeta processed/ del bucket sisfall de S3. Están en esta carpeta para que se puedan reproducir localmente luego en el jupyter notebook clonando el repositorio de github.

entrenamiento_sisfall_jupyter_notebook_local.ipynb: Notebook principal que documenta todo el proceso: carga híbrida (S3/Local), entrenamiento del modelo Random Forest, entrenamiento del modelo XGBoost, optimización de hiperparámetros (GridSearch) y evaluación (Matriz de Confusión y Casos de Uso).

entrenamiento_sisfall_jupyter_notebook_local.ipynb:
Este notebook está diseñado con una arquitectura híbrida para garantizar su reproducibilidad técnica tanto en mi entorno de nube (AWS) como en entornos locales para su evaluación (Google Colab).
El código de las celdas de busqueda de los mejores parametros con GridSearch, tanto para Random Forest como para XGBoost está como comentario para que no se ejecute cada vez dado que tarda mucho tiempo.

Nota sobre la Reproducibilidad: Las métricas documentadas en la memoria del proyecto fueron generadas en el entorno original de AWS SageMaker IA. Al ejecutar este notebook en Google Colab, es posible observar ligeras variaciones en las matrices de confusión o decimales de precisión. Esto es un comportamiento esperado debido a las diferencias en las versiones de las librerías del entorno virtual de Colab y a la estocasticidad inherente de los algoritmos de ensamblaje (XGBoost/Random Forest).

Se ha subido tambien al repositorio github el entrenamiento_sisfall_sagemaker_IA.ipynb que es el original que se ha ejecutado en AWS SageMaker IA.

Librerías principales: Pandas, Scikit-learn, XGBoost, Boto3, Joblib

Entornos: AWS SageMaker, Google Colab
