# 🧠 Predicción del Costo de Seguro Médico con Machine Learning

Este proyecto aplica un pipeline completo de ciencia de datos para predecir el costo de un seguro médico en función de características personales como edad, IMC y hábito de fumar. Incluye limpieza, visualización, modelado, comparación de algoritmos y despliegue interactivo con Streamlit.

> ✅ Proyecto ejecutado desde Google Colab y optimizado para uso profesional en GitHub y Streamlit.

---

## 📌 Objetivos

- Analizar los factores que influyen en el costo del seguro médico.
- Aplicar técnicas de ETL y EDA para preparar los datos.
- Comparar distintos modelos de regresión (Lineal, Random Forest, XGBoost).
- Desplegar un modelo funcional en una app interactiva para estimación directa.

---

## 🧾 Dataset utilizado

- 📂 **Fuente**: [Medical Cost Personal Dataset - Kaggle](https://www.kaggle.com/datasets/mirichoi0218/insurance)
- 🧠 **Filas**: 1338 registros de pacientes
- 🔤 **Variables**:
  - `age`: Edad del paciente
  - `sex`: Sexo
  - `bmi`: Índice de masa corporal
  - `children`: Número de hijos
  - `smoker`: ¿Fumador?
  - `region`: Región geográfica
  - `charges`: Costo real del seguro

---

## 🔍 Análisis exploratorio (EDA)

- Detección de outliers con boxplots y reglas estadísticas (IQR).
- Visualización de correlaciones y distribución por clases (`smoker`).
- Comparación entre clases usando `lmplot` para visualizar tendencias:

---

## 🧠 Modelado y resultados

Se evaluaron 3 modelos principales para predecir el logaritmo del costo (`log(charges)`):

| Modelo             | MAE      | RMSE     | R²     |
|--------------------|----------|----------|--------|
| Regresión Lineal   | 3888.44  | 7814.06  | 0.6067 |
| XGBoost            | 2506.02  | 4997.43  | 0.8391 |
| **Random Forest**  | **2085.10**  | **4369.68**  | **0.8770** ✅ |

El modelo final fue **Random Forest con salida log-transformada**, por su alto rendimiento y generalización.

---

## 📊 Importancia de Variables

```text
1. smoker         → > 40%
2. age            → ~ 40%
3. bmi            → > 10%
4. others         → < 5%
