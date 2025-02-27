# Predicción de Producción de Pozos 🚀⛽

## 📌 Descripción del Proyecto
Este proyecto desarrolla un modelo de **predicción de producción de pozos** utilizando **Machine Learning**. Se busca estimar variables clave del proceso de extracción, como el **factor de recuperación, el pico de producción y la eficiencia del sistema**, con base en datos históricos de inyección de vapor y producción de crudo.

---

## 📊 Datos Utilizados

<details>
  <summary>🔍 Ver detalles</summary>

- **Inyección de vapor:** Datos acumulados y por ciclo
- **Producción de crudo:** Historial de producción
- **SOR (Steam-Oil Ratio):** Relación entre vapor inyectado y producción de crudo
- **Picos de producción:** Máximos de producción por ciclo

</details>

---

## 🏗️ Metodología

<details>
  <summary>⚙️ Procesamiento de datos</summary>

1. **Limpieza de datos**: Manejo de valores nulos y outliers
2. **Creación de variables**: Se generaron variables como:
   - `BWEiny_ciclo`: Diferencia consecutiva (.diff()) de inyección acumulada
   - `SOR_lag`: Desplazamiento (shift(1)) del SOR
   - `pico_lag`: Pico de producción del ciclo anterior
3. **División de datos**: Train/Test en un 80/20

</details>

<details>
  <summary>📈 Modelado</summary>

1. **Modelos evaluados:**
   - **Regresión Lineal Múltiple**
   - **Redes Neuronales**
   - **CatBoost**
   - **MultiOutputRegressor con RandomForest**
2. **Selección del mejor modelo:**
   - Se compararon métricas como RMSE, R² y MAE
   - **MultiOutputRegressor fue el mejor** debido a su capacidad para manejar múltiples salidas de manera independiente

</details>

<details>
  <summary>🔧 Tuning de Hiperparámetros</summary>

Se utilizó GridSearchCV y RandomizedSearchCV para optimizar:
- Número de árboles en el bosque (n_estimators)
- Profundidad máxima de los árboles (max_depth)
- Mínimo de muestras por hoja (min_samples_leaf)

</details>

---

## 🚀 Resultados

<details>
  <summary>📊 Métricas del mejor modelo</summary>

- **RMSE:** *Valor óptimo*
- **R²:** *Buena capacidad predictiva*
- **MAE:** *Error promedio bajo*
- **Predicción confiable** de producción futura basada en ciclos anteriores

</details>

---

## 🛠️ Requisitos

<details>
  <summary>📌 Instalación</summary>

### Clonar el repositorio:
```bash
 git clone https://github.com/tu_usuario/PrediccionProduccionPozos.git
```

### Instalar dependencias:
```bash
 pip install -r requirements.txt
```
</details>

---

## 📌 Uso del Modelo

<details>
  <summary>🖥️ Ejecución</summary>

1. Cargar los datos en `data/`
2. Ejecutar los notebooks en `notebooks/`
3. Ajustar hiperparámetros si es necesario
4. Predecir con el modelo entrenado

</details>

---

## 📌 Contribuciones

¡Cualquier contribución es bienvenida! Puedes hacer un **fork** y enviar un **pull request**. 😊

---
