# 🏦 Predicción de Abandono de Clientes (*Churn*) Bancario

## 💡 Introducción y Objetivo del Proyecto

Este proyecto se enfoca en el desarrollo de un modelo de **Clasificación de Machine Learning** para predecir la probabilidad de que un cliente bancario abandone el servicio (*churn*).

El objetivo principal es transformar los datos de los clientes en un sistema predictivo capaz de identificar a los clientes en riesgo, permitiendo a la institución tomar **medidas de retención** proactivas.

---

## 🛠️ Tecnologías y Librerías

El análisis fue ejecutado en un entorno de **Jupyter Notebook** utilizando Python.

| Categoría | Librerías | Propósito |
| :--- | :--- | :--- |
| **Análisis de Datos** | `pandas`, `numpy` | Carga, limpieza y manipulación de datos. |
| **Visualización** | `plotly`, `seaborn`, `matplotlib` | Análisis exploratorio (EDA) y visualización de resultados (Matriz de Confusión). |
| **Machine Learning** | `sklearn` | Preprocesamiento, modelado (Árboles de Decisión, KNN), y evaluación. |

### Instalación de Dependencias

Para replicar el entorno de trabajo, puedes instalar las librerías necesarias:

```bash
pip install pandas numpy scikit-learn plotly seaborn matplotlib
````

-----

## 📊 Metodología de Machine Learning

El proyecto siguió un flujo de trabajo estándar para la clasificación:

### 1\. Análisis Exploratorio de Datos (EDA)

  * **Inspección de Datos:** Se verificó la calidad de la base de datos de 10,000 registros, confirmando la ausencia de valores nulos.
  * **Análisis Descriptivo:** Exploración de variables categóricas (`país`, `sexo_biologico`) y numéricas (`saldo`, `edad`) en relación con la variable objetivo (`churn`).

### 2\. Preprocesamiento y Transformación

  * **Limpieza:** Eliminación de la columna no relevante (`id_cliente`).
  * **Codificación:** Aplicación de **One-Hot Encoding** a las variables categóricas utilizando `sklearn.compose.make_column_transformer`.
  * **Normalización:** Aplicación de `MinMaxScaler` para el entrenamiento del modelo KNN, ya que este algoritmo se basa en el cálculo de distancias.

### 3\. Modelado y Evaluación

Se entrenaron tres modelos de clasificación, y su rendimiento se comparó mediante la métrica de **Exactitud (Accuracy)** en el conjunto de prueba:

| Modelo | Exactitud (Accuracy) | Notas |
| :--- | :--- | :--- |
| **Modelo de Referencia (Baseline)** | 79.64% | Métrica base para comparación. |
| **K-Nearest Neighbors (KNN)** | 81.96% | Buen rendimiento tras la normalización de datos. |
| **Árbol de Decisión** | **84.64%** | **Modelo Campeón** con la mejor generalización. |

-----

## 🏆 Resultados Clave y Conclusión

### Modelo Ganador: Árbol de Decisión

El **Modelo de Árbol de Decisión** fue seleccionado como el **"Modelo Champion"** por ofrecer el mayor rendimiento predictivo (84.64% de exactitud).

  * **Validación:** Se utilizó la **Matriz de Confusión** para evaluar la capacidad del modelo para clasificar correctamente los casos de *churn* (Positivos Verdaderos) y no-*churn* (Negativos Verdaderos).
  * **Explicabilidad:** Se analizó la importancia de las características, lo que permite a los equipos de negocio entender qué factores (ej. `edad`, `score_credito`) impulsan la cancelación del servicio.
  * **Serialización:** El modelo campeón y el transformador de datos (`onehotencoder`) fueron **serializados (.pkl)** para su posterior despliegue en un entorno de producción, listo para clasificar nuevos datos de clientes.

### Despliegue (Ejemplo de Predicción)

El modelo está listo para clasificar nuevos clientes, como en el siguiente ejemplo, donde predice correctamente que un cliente con un score de 850 **no presentará *churn*** (Predicción: 0).

-----

## 🧑 Autor

  * [Ny-dia](https://www.google.com/search?q=https://github.com/Ny-dia)

<!-- end list -->

```
```
