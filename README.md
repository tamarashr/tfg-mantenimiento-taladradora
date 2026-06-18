# TFG — Mantenimiento industrial 4.0. Aplicación a la detección y clasificación de los modos de fallo de una máquina taladradora

Trabajo de Fin de Grado centrado en el **mantenimiento predictivo** aplicado a una máquina taladradora. El proyecto desarrolla y compara distintos modelos de **aprendizaje automático** para predecir los modos de fallo de la herramienta.

## Descripción

A partir de un conjunto de datos sintético de un proceso de taladrado, el trabajo aborda el ciclo completo de un problema de clasificación: análisis exploratorio, preprocesamiento, entrenamiento y comparación de modelos, interpretabilidad y validación sobre casos individuales. Finalmente se incluye una pequeña interfaz interactiva para realizar predicciones.

Los cuatro modos de fallo considerados son:

- Filo recrecido (*Build-up edge failure*)
- Virutas comprimidas (*Compression chips failure*)
- Desgaste de flanco (*Flank wear failure*)
- Herramienta incorrecta (*Wrong drill bit failure*)

## Modelos implementados

| Modelo | Tipo |
|---|---|
| Regresión logística | Modelo de referencia (*baseline*) |
| Random Forest | Ensamblaje (*bagging*) |
| XGBoost | Ensamblaje (*boosting*) |
| Red neuronal MLP | Aprendizaje profundo |

La comparación se realiza prestando especial atención a las métricas *recall macro* y *F1 macro*.

## Conjunto de datos

Se emplea el **Explainable AI (XAI) Drilling Dataset**, elaborado por Wallsberger, Knauer y Matzka (HTW Berlín). El notebook descarga automáticamente el dataset desde Kaggle mediante `kagglehub`, por lo que no es necesario descargarlo manualmente.

- Dataset: https://www.kaggle.com/datasets/raphaelwallsberger/xai-drilling-dataset
- Publicación: R. Wallsberger, R. Knauer, S. Matzka, *Explainable Artificial Intelligence in Mechanical Engineering: A Synthetic Dataset for Comprehensive Failure Mode Analysis*, 2023 Fifth International Conference on Transdisciplinary AI (TransAI).  
DOI: http://dx.doi.org/10.1109/TransAI60598.2023.00032

## Estructura del notebook

El trabajo está formado por un único notebook, `tfg_taladradora.ipynb`, organizado en las siguientes secciones:

1. Introducción y descripción del problema
2. Análisis exploratorio de datos (EDA)
3. Preprocesamiento e ingeniería de características
4. Modelado y evaluación comparativa
5. Interpretabilidad (XAI con SHAP) e inferencia sobre casos individuales
6. Diseño de la aplicación e interfaz

## Cómo ejecutar el código

El código se ha realizado en **Google Colab**, y se recomienda ejecutarlo en esta plataforma. Los pasos a seguir son:

1. Descargar `tfg_taladradora.ipynb`.
2. Abrir `tfg_taladradora.ipynb` en Google Colab.
3. Ejecutar todas las celdas: `Entorno de ejecución → Ejecutar todo` (`Runtime → Run all`).

El propio notebook instala las librerías que no vienen por defecto (`imbalanced-learn` y `gradio`) y descarga el dataset desde Kaggle.

## Principales librerías

- **NumPy** y **Pandas** — manipulación y análisis de datos
- **Matplotlib** y **Seaborn** — visualización
- **Scikit-learn** — preprocesamiento, modelos y métricas
- **XGBoost** — modelo de *gradient boosting*
- **TensorFlow / Keras** — red neuronal MLP
- **Imbalanced-learn** — tratamiento del desbalanceo (SMOTETomek)
- **SHAP** — interpretabilidad de los modelos (XAI)
- **Joblib** — almacenamiento de los modelos entrenados
- **Gradio** — interfaz de predicción interactiva

## Licencia

El código de este repositorio se distribuye bajo la licencia **MIT** (ver archivo `LICENSE`).

La memoria del Trabajo de Fin de Grado se acoge a una licencia **Creative Commons BY-NC-ND**.

## Autora
Tamara Sabrina Heredia Real  
Trabajo de Fin de Grado — Escuela de Ingenierías Industriales (Universidad de Málaga)  
Curso 2025-2026
