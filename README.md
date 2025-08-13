# Challenge-TelecomX-Part-2

# Predicción de Churn en Clientes de Telecomunicaciones

Este proyecto analiza datos de clientes de una empresa de telecomunicaciones para **predecir la probabilidad de abandono (churn)** utilizando diferentes modelos de Machine Learning.  
El objetivo es identificar patrones asociados al churn y construir modelos que permitan diseñar estrategias de retención más efectivas.

---

## 📂 Contenido del proyecto

- `datos_tratados.csv` → Dataset preprocesado listo para modelar.
- `Telecom_X_Parte_2.ipynb` → Notebook con análisis exploratorio, preprocesamiento, modelado y evaluación.
- `README.md` → Este documento.

---

## 📊 Análisis exploratorio (EDA)

Se identificaron patrones relevantes:

- **Tipo de contrato**:  
  - Mes a mes → 42.7% de churn (riesgo alto)  
  - 1 año → 11.4%  
  - 2 años → 2.9%
  
- **Método de pago**:  
  - Electronic Check → 45.3% de churn (riesgo alto)  
  - Otros métodos → menor churn

- **Facturación electrónica**:  
  - Sí → 33.6% churn  
  - No → 16.4% churn

- **Tenure**: Correlación negativa (-0.35) con churn: clientes más antiguos son más fieles.
- **Cargo mensual**: Correlación positiva (+0.19) con churn.

---

## 🤖 Modelos y resultados

### 1. **Random Forest**
- Exactitud: **0.779**
- ROC AUC: **0.821**
- Recall (churn): **0.60**
- Mejor en balance general entre precisión y recall, con menos falsos positivos que la regresión logística.

### 2. **Regresión Logística**
- Exactitud: **0.751**
- ROC AUC: **0.845**
- Recall (churn): **0.81**
- Mejor para **detectar churners** (menos falsos negativos), aunque con más falsos positivos.

---

## 📌 Conclusiones

- Si la prioridad es **detectar la mayor cantidad posible de clientes en riesgo**, usar **Regresión Logística**.
- Si la prioridad es **equilibrar precisión y recall para evitar contactar a demasiados clientes que no se irán**, usar **Random Forest**.
- Estrategias de retención deben enfocarse en clientes:
  - Con contrato mes a mes
  - Que pagan por Electronic Check
  - Con facturación electrónica activada
  - De corta antigüedad

---

## 🚀 Uso

1. Clonar este repositorio:
   ```bash
   git clone https://github.com/Malcuthrad/Challenge-TelecomX-Part-2
2. Instalar dependencias:
   ```bash
   pip install -r requirements.txt
   ```
3. Abrir el notebook:
   ```bash
   jupyter notebook Telecom_X_Parte_2.ipynb
   ```

---

## 🛠️ Tecnologías utilizadas
- Python 3.x
- Pandas, NumPy
- Matplotlib, Seaborn
- Scikit-learn
- Jupyter Notebook

---

## 📄 Licencia
Este proyecto se distribuye bajo la licencia MIT. Puedes usarlo, modificarlo y distribuirlo libremente.
