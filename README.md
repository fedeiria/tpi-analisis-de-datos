# Predicción de cancelación de clientes (Churn) en una empresa de telecomunicaciones

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/fedeiria/tpi-analisis-de-datos/blob/main/notebooks/TPI_Analisis_de_Datos.ipynb)

- **Trabajo:** Trabajo Práctico Integrador (TPI)
- **Materia:** Introducción al Análisis de Datos
- **Institución:** Universidad Tecnológica Nacional, Facultad Regional Avellaneda
- **Cursada:** 2º cuatrimestre de 2026
- **Docente:** Enzo Martín Zotti

---

## Problema de negocio

Una empresa de telecomunicaciones pierde cada mes una parte de sus clientes, que cancelan el servicio y se van a la competencia (*churn*). Como retener a un cliente suele ser más barato que conseguir uno nuevo, a la empresa le conviene **detectar a tiempo qué clientes tienen mayor riesgo de irse** para dirigirles acciones de retención.

**Pregunta de negocio:** ¿qué características de los clientes y de sus contratos están asociadas a la cancelación, y es posible anticiparla a partir de los datos?

## Integrantes

| Integrante | División |
|---|---|
| Martin Allende | 343 |
| Federico Iriarte | 343 |
| Tomas Munilla | 343 |
| Lautaro Guzzio | 343 |

## Principales resultados

- **1 de cada 4 clientes (26,5%) cancela** el servicio.
- El **tipo de contrato** es el factor más asociado a la cancelación: 42,7% en el contrato mes a mes contra 2,8% en el de dos años.
- Los **primeros meses** de la relación son el período crítico, y el pago con **cheque electrónico** y la **fibra óptica** concentran el riesgo.
- **Regresión lineal simple** (`Tenure` → `TotalCharges`): R² = 0,66 y MAE = 876.
- **Clasificación de Churn** (regresión logística): accuracy de 80,4% (frente a 73,5% de referencia) y recall de 55,6% para la clase "Cancela".

El detalle completo del análisis se encuentra en el notebook y en el informe ejecutivo.

## Stack tecnológico

| Herramienta | Uso en el proyecto |
|---|---|
| **Python 3** | Lenguaje principal |
| **Pandas** | Carga, manipulación, limpieza e integración de datos |
| **NumPy** | Cálculos numéricos |
| **Matplotlib** y **Seaborn** | Visualización de datos |
| **Scikit-Learn** | Preprocesamiento (`ColumnTransformer`, `OneHotEncoder`, `OrdinalEncoder`, `StandardScaler`), partición `train_test_split`, `Pipeline` y modelos (`LinearRegression`, `LogisticRegression`) |
| **Google Colab** | Entorno de ejecución reproducible |
| **Git** y **GitHub** | Control de versiones y publicación del proyecto |

## Estructura del repositorio

```
tpi-analisis-de-datos/
├── data/
│   ├── raw/                      # Dataset original (WA_Fn-UseC_-Telco-Customer-Churn.csv)
│   └── processed/                # Dataset depurado, transformado e integrado (telco_churn_clean.csv)
├── notebooks/
│   └── TPI_Analisis_de_Datos.ipynb   # Notebook oficial ejecutable en Google Colab
├── docs/
│   └── INFORME_EJECUTIVO.pdf     # Informe técnico-ejecutivo y de resultados
└── README.md                     # Portada del proyecto, tecnologías, integrantes y enlace a Colab
```

## Cómo explorar el proyecto

1. **Ejecutar el notebook:** hacé clic en el badge **"Open in Colab"** de arriba y luego en *Entorno de ejecución → Ejecutar todo*. No requiere instalar nada: el dataset se descarga automáticamente desde este repositorio.
2. **Recorrer el análisis:** el notebook está organizado en secciones que siguen la consigna del TPI:
   - **0.** Configuración del entorno y carga de datos
   - **1-3. Fundamentos, manipulación y limpieza:** problema de negocio, hipótesis, clasificación de variables, filtrado, agregación, transformación, integración, tratamiento de faltantes, dtypes y outliers
   - **4-5. Análisis exploratorio y visualización:** estadística descriptiva, correlaciones de Pearson y Spearman, análisis categórico, contraste de hipótesis y gráficos
   - **6-8. Preprocesamiento y modelado:** codificación, escalado, partición estratificada, regresión lineal simple y clasificación de Churn
   - **9.** Conclusiones y recomendaciones de negocio
3. **Leer el informe:** las conclusiones y la metodología están desarrolladas en [`docs/INFORME_EJECUTIVO.pdf`](docs/INFORME_EJECUTIVO.pdf).

## Origen de los datos

[Telco Customer Churn](https://www.kaggle.com/datasets/blastchar/telco-customer-churn) (Kaggle): registro de 7.043 clientes de una empresa de telecomunicaciones, con variables sociodemográficas, características de contratación, facturación y estado de cancelación (`Churn`).
