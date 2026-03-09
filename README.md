# 📊 Predicción de Churn de Clientes

## 📌 Descripción del Proyecto

Este proyecto tiene como objetivo analizar y predecir el **churn de clientes** en una empresa de telecomunicaciones. El churn ocurre cuando un cliente decide **cancelar su servicio**, lo que representa un desafío importante para las empresas que dependen de suscripciones.

A través de **análisis exploratorio de datos (EDA)** y **modelos de machine learning**, se busca identificar los factores que influyen en la cancelación del servicio y construir modelos capaces de **predecir qué clientes tienen mayor probabilidad de abandonar la empresa**.

---

# 🎯 Objetivos

Los principales objetivos del proyecto son:

* Analizar los patrones asociados al churn de clientes.
* Identificar las variables que influyen en la cancelación del servicio.
* Construir modelos predictivos para identificar clientes en riesgo.
* Comparar diferentes modelos de clasificación.
* Proponer recomendaciones basadas en datos para mejorar la retención de clientes.

---

# 📂 Dataset

El dataset contiene información sobre clientes de una empresa de telecomunicaciones, incluyendo variables relacionadas con:

* Información demográfica del cliente
* Tipo de contrato
* Servicios contratados
* Tipo de conexión a internet
* Método de pago
* Cargos mensuales y totales
* Soporte técnico
* Estado de churn

### Variable objetivo

**Churn**

* `1` → el cliente canceló el servicio
* `0` → el cliente continúa con el servicio

---

# 🔎 Análisis Exploratorio de Datos (EDA)

Durante el análisis exploratorio se identificaron varios patrones importantes:

* Los clientes con **contrato Month-to-Month presentan mayor churn**.
* Los clientes con **menor antigüedad (tenure)** tienen mayor probabilidad de cancelar el servicio.
* Los clientes con **Internet de fibra óptica** presentan una tasa de churn más alta.
* El método de pago **Electronic Check** está asociado con mayor abandono.
* Los clientes que **no tienen soporte técnico o seguridad online** presentan mayor churn.

Estos hallazgos ayudaron a entender mejor el comportamiento de los clientes y orientar el desarrollo del modelo predictivo.

---

# 🤖 Modelos de Machine Learning

Se probaron diferentes modelos de clasificación para predecir el churn de clientes.

### Modelos implementados

* Regresión Logística
* Regresión Logística con balance de clases
* Random Forest
* Decision Tree

Debido al **desbalance en las clases del dataset**, se utilizó el parámetro:

```
class_weight="balanced"
```

para mejorar la capacidad del modelo de detectar clientes que abandonan el servicio.

---

# 📊 Evaluación de Modelos

Los modelos se evaluaron utilizando métricas como:

* Accuracy
* Precision
* Recall
* F1-score
* Matriz de confusión

Comparación general de resultados:

| Modelo                         | Accuracy | Recall Churn |
| ------------------------------ | -------- | ------------ |
| Regresión Logística            | ~0.80    | ~0.54        |
| Regresión Logística balanceada | ~0.73    | **~0.78**    |
| Random Forest                  | ~0.78    | ~0.45        |
| Decision Tree                  | ~0.73    | ~0.49        |

El modelo de **Regresión Logística con balance de clases** mostró el mejor desempeño para detectar clientes que cancelan el servicio.

---

# 📈 Variables más influyentes en el churn

Según el modelo de regresión logística, las variables que más influyen en el churn incluyen:

### Factores que aumentan el churn

* InternetService_Fiber optic
* PaymentMethod_Electronic check
* PaperlessBilling
* Servicios de streaming
* MultipleLines
* SeniorCitizen

### Factores que reducen el churn

* Contract_Two year
* Contract_One year
* OnlineSecurity
* TechSupport
* Mayor antigüedad del cliente (tenure)

---

# 💡 Recomendaciones

A partir del análisis realizado se proponen las siguientes estrategias para reducir el churn:

* Incentivar contratos de **mayor duración**.
* Promover **métodos de pago automáticos** en lugar de Electronic Check.
* Mejorar el **soporte técnico y servicios de seguridad online**.
* Revisar la experiencia del cliente en el servicio de **fibra óptica**.
* Implementar estrategias de retención para **clientes nuevos**.

---

# 🛠 Tecnologías Utilizadas

* Python
* Pandas
* Scikit-learn
* Matplotlib
* Seaborn
* Jupyter Notebook

---

# 📁 Estructura del Proyecto

```
churn-prediction/
│
├── data/
├── notebooks/
│   └── churn_analysis.ipynb
│
├── README.md
```

---

# 📈 Conclusión

El churn de clientes está influenciado por múltiples factores relacionados con el tipo de contrato, el servicio de internet, el método de pago y la disponibilidad de soporte técnico.

El modelo de **regresión logística con balance de clases** mostró un buen desempeño al identificar clientes en riesgo de abandonar el servicio, lo que permite a la empresa implementar estrategias de retención más efectivas.

