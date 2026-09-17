# 📞 Análisis de Uso y Segmentación de Clientes - ConnectaTel

## 🎯 Objetivo del Proyecto
El objetivo principal de este proyecto es analizar el comportamiento de uso de servicios móviles (llamadas y mensajes de texto) de los clientes de **ConnectaTel** en Latinoamérica durante el año 2024. A través de este análisis se identifican patrones de consumo, se detectan e interpretan datos atípicos (*outliers*), y se construyen segmentaciones de clientes para proponer estrategias comerciales de retención y optimización de planes.

---

## 🛠️ Tecnologías y Librerías Utilizadas
* **Lenguaje:** Python 3.x
* **Entorno:** Jupyter Notebook / Google Colab
* **Librerías principales:**
  * `pandas` - Carga, limpieza y manipulación de datos
  * `numpy` - Cálculos numéricos y lógica condicional
  * `matplotlib` & `seaborn` - Visualizaciones de distribución, boxplots y gráficos de barras

---

## 📂 Estructura de la Base de Datos
El proyecto integra información de tres fuentes principales:
1. `plans.csv`: Catálogo de planes (Básico y Premium), precios y beneficios incluidos.
2. `users_latam.csv`: Información demográfica de clientes (edad, ciudad, fecha de registro, plan).
3. `usage.csv`: Registro histórico de llamadas (duración) y mensajes (longitud).

---

## 📊 Pasos del Análisis y Hallazgos Clave

### 1. Limpieza y Calidad de Datos
* **Valores Sentinels:** Se corrigieron valores de edad `-999` imputándolos con la mediana del conjunto (47 años).
* **Estandarización:** Se reemplazaron caracteres incompletos en ciudades (`'?'`) por valores nulos (`NA`).
* **Fechas Inconsistentes:** Se identificaron y reemplazaron registros con fechas futuras (año 2026) por `NaT`.

### 2. Tratamiento de Outliers
* Se evaluaron los límites mediante el **Rango Intercuartílico (IQR)** para las variables `cant_mensajes`, `cant_llamadas` y `cant_minutos_llamada`.
* **Decisión:** Se optó por **mantener los valores atípicos** debido a que no corresponden a errores de medición, sino a patrones reales de consumo de un grupo de **Power Users**.

### 3. Segmentación de Clientes
* **Por Edad:** La distribución de llamadas y mensajes es uniforme entre los rangos de edad (Jóvenes, Adultos y Adultos Mayores), demostrando que la edad no condiciona la intensidad de uso.
* **Por Intensidad de Uso:** Se clasificó a la población en tres niveles:
  * **Bajo uso:** Actividad reducida o esporádica.
  * **Uso medio:** Representa a la mayoría de la base de clientes (consumo estándar).
  * **Alto uso:** Clientes con demanda intensiva de servicio (*Power Users*).

---

## 💡 Se plantearon Recomendaciones Comerciales
1. **Up-selling Progresivo:** Diseñar campañas de migración hacia planes *Premium* para los usuarios de **Uso medio** que rozan los límites de su plan.
2. **Fidelización de Power Users:** Crear incentivos de retención para el segmento de **Alto uso**, asegurando la permanencia de los clientes con mayor consumo.
3. **Optimización de Campañas:** Enfocar la pauta publicitaria en la intensidad de consumo en lugar de segmentar por edad demográfica.
