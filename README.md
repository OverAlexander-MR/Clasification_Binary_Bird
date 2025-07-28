# Clasificación Binaria utilizando Machine Learning para la detección de Aves en Bioacustica
### Autores: Over Alexander Mejia Rosado y Ronald Mateo Ceballos Lozano
### Asignatura: Aprendizaje Maquinal
Como proyecto de la asignatura Aprendizaje Maquinal, se decidio desarrollar un clasificador binario por cada clase del dataset que sea capaz de determinar si un audio contiene vocalizaciones de animales como Aves, Anfibios, Mamiferos o Insectos. Para ello se tomo como referencia el dataset de la competencia BirdCLEF+ 2025 de Kaggle con las siguientes caracteristicas:

### Dataset:
El dataset cuenta con un total de 28564 grabaciones con etiquetas y 9726 sin etiquetas, en total son 209 especies divididas en la siguientes clases:

### Aves: 146 especies --- 27648 muestras
### Anfibios: 34 especies --- 583 muestras
### Mamiferos: 17 especies --- 155 muestras
### Insectos: 9 especies --- 178 muestras

### Clasificadores Binarios de Aves, Amphibia, Mammalia, Insecta:
Para el uso de los clasificadores binarios, se debe dirigir a la carpeta referente a la clase del clasificador que se desea anlizar, por ejemplo `Clasificadores_Binarios\Aves`, en esta se encuentra un cuaderno en Jupyter llamado `Clasificadores_Aves` y dentro se encuentran los 3 modelos con su respectivo procesamiento.

### Clasificadores de Especies de Aves, Amphibia, Mammalia, Insecta:

# Librerias de Python usadas
`Pandas`
`Numpy`
`Scikit-Learn`
`Seaborn`
`Xgboost`
`Optuna`
`Imblearn`

## Visualización de los Hiperparámetros en el Dahsboard de Optuna 
Durante el proceso de optimización de hiperparámetros para cada clasificador binario, se utilizó Optuna como herramienta de búsqueda basada en optimización bayesiana. Para facilitar el análisis y comparación de los resultados obtenidos por cada ensayo (trial), se habilitó el dashboard interactivo de Optuna mediante el comando:

`optuna-dashboard sqlite:///optuna_tuning.db`

Este debe ser ejecutado en una terminal abierta con la carpeta dentro de la carpeta `Tuning_Optuna_Clasificadores_Binarios` e ingresar a la carpeta de la clase y luego a la del tipo de procesamiento que se desea analizar por medio del dashboard, en esa carpeta se encuentra el archivo `optuna_tuning.db`. Esto despliega una interfaz web local en la dirección `(http://127.0.0.1:8080/)`, desde la cual se puede observar:

## La evolución del valor objetivo (AUC-ROC) a lo largo de los ensayos.
## La importancia relativa de los hiperparámetros mediante Hyperparameter Importance.
## La distribución y correlación de los hiperparámetros más influyentes.
## El historial de exploración de valores con Parallel Coordinates y Slice plots.

Este dashboard fue clave para comprender qué configuraciones de hiperparámetros fueron más efectivas para cada tipo de clasificador (Random Forest, XGBoost, SVM y Regresión Logística) y cada grupo animal (Aves, Anfibios, Mamíferos e Insectos).
