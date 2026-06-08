# Retail-Sales-Classification
# Predicción de Ventas en una Tienda de Retail mediante Machine Learning

## Descripción del Proyecto

El objetivo de este proyecto fue desarrollar y evaluar modelos de clasificación supervisada capaces de predecir si una transacción corresponde a una venta alta o una venta baja en una tienda de retail.

La variable objetivo (**High_Sales**) fue construida a partir del monto total de la compra, clasificando las transacciones en dos categorías:

* Venta Baja = 0
* Venta Alta = 1

La variable Total Amount fue eliminada durante el entrenamiento para evitar fuga de información (data leakage).

Se aplicaron distintas técnicas de preprocesamiento, ingeniería de variables y benchmarking de modelos de Machine Learning para identificar el algoritmo con mejor desempeño predictivo.

---

## Dataset

El conjunto de datos contiene información de 1.000 transacciones de una tienda de retail e incluye variables demográficas, comerciales y temporales.

Variables originales:

* Transaction ID
* Customer ID
* Gender
* Age
* Product Category
* Quantity
* Price per Unit
* Total Amount
* Date

---

## Preprocesamiento

Se realizaron las siguientes transformaciones:

* Conversión de fecha a formato datetime.
* Creación de variables temporales:

  * Month
  * Day
  * DayOfWeek
* Eliminación de identificadores:

  * Transaction ID
  * Customer ID
* Exclusión de Total Amount para evitar fuga de información.
* Codificación One-Hot Encoding para variables categóricas.
* Estandarización mediante StandardScaler para variables numéricas.
* División Train/Test (70%-30%).

---

## Modelos Evaluados

Se compararon los siguientes algoritmos:

1. Logistic Regression
2. K-Nearest Neighbors (KNN)
3. Decision Tree
4. Random Forest
5. XGBoost
6. LightGBM

---

## Resultados

| Modelo              | Accuracy | ROC-AUC |
| ------------------- | -------- | ------- |
| KNN                 | 52%      | 53%     |
| Random Forest       | 52%      | 52%     |
| LightGBM            | 51%      | 49%     |
| XGBoost             | 49%      | 50%     |
| Decision Tree       | 49%      | 49%     |
| Logistic Regression | 44%      | 43%     |

El modelo KNN obtuvo el mejor desempeño, alcanzando una exactitud del 52% y un ROC-AUC de 53%.

Sin embargo, los resultados evidencian una capacidad predictiva limitada, sugiriendo que las variables disponibles contienen poca información para diferenciar ventas altas y bajas.

---

## Estructura del Repositorio

Retail-Sales-Classification
│
├── data
│   └── retail_sales_dataset.csv
│
├── notebooks
│   └── Proyecto1_ParteFinal.ipynb
│
├── reports
│   ├── classification_report.png
│   ├── Matriz de Confusión - KNN.png
│   └── Curva ROC-KNN.png
│
├── presentation
│   └── one-page.pdf
│
├── README.md
└── .gitignore

---
### data

Contiene el dataset utilizado en el proyecto.

### notebooks

Incluye el notebook completo con:

* Exploración de datos
* Preprocesamiento
* Entrenamiento de modelos
* Evaluación de desempeño

### reports

Contiene:

* Informe de clasificación
* Matriz de confusión
* Curva ROC

### presentation

Contiene la presentación ejecutiva One-Page del proyecto.

---

## Instrucciones para Ejecutar

1. Clonar el repositorio.

```bash
git clone <url-del-repositorio>
```

2. Instalar dependencias.

```bash
pip install -r requirements.txt
```

3. Abrir el notebook.

```bash
jupyter notebook
```

4. Ejecutar todas las celdas del archivo:

```text
Proyecto1_Clasificacion_Ventas.ipynb
```

---
## Tecnologías Utilizadas

- Python
- Pandas
- NumPy
- Scikit-Learn
- XGBoost
- LightGBM
- Matplotlib
- GitHub

---  
## Autora

Karla Caroca Henríquez

---

## Licencia

Proyecto desarrollado con fines académicos.
