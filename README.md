# telecom-analysis
Análisis de ConnectaTel (hasta 2024): consolidamos plans, users y usage en user_profile. Mantuvimos outliers (hasta 155 min y 17 msjs) por ser heavy users reales. Segmentamos por uso y edad: el 50% son Adultos y el 72.5% tiene Uso Medio. Se sugiere adaptar planes a este núcleo y crear ofertas Unlimited para retener al segmento alto.
# Análisis Exploratorio de Datos (EDA) y Segmentación de Clientes - ConnectaTel

## 🎯 Objetivo del Proyecto
El objetivo principal de este proyecto es realizar un Análisis Exploratorio de Datos (EDA) sobre el consumo telefónico y los perfiles de los usuarios de **ConnectaTel**. A través de la limpieza, consolidación y segmentación de datos, se busca identificar patrones de uso (llamadas y mensajes) y comportamientos por rango de edad para generar hallazgos y recomendaciones estratégicas que optimicen la oferta de planes comerciales.

## 📊 Datasets Utilizados
* **`users_latam.csv`**: Contiene la información demográfica de los usuarios (`user_id`, `age`, `city`, `plan`, `reg_date`, `churn_date`).
* **`usage.csv`**: Registra eventos de consumo individual de llamadas y mensajes por cliente.
* **`user_profile` (DataFrame Consolidado)**: Tabla resultante tras el procesamiento y agregación de consumo por cliente, incorporando métricas como `cant_mensajes`, `cant_llamadas` y `cant_minutos_llamada`, además de los segmentos creados (`grupo_uso` y `grupo_edad`).

## 🛠️ Etapas del Análisis
1. **Carga y Exploración Inicial:** Evaluación de estructuras de datos, tipos de variables y detección de valores nulos (como en `churn_date`, correspondiente a usuarios activos).
2. **Procesamiento y Limpieza:** Consolidación de fuentes de datos (`merge` y `groupby`) para estructurar la tabla `user_profile`.
3. **Análisis de Outliers (Límites IQR):** Identificación y justificación de valores atípicos en variables de consumo (`cant_mensajes`, `cant_llamadas`, `cant_minutos_llamada`), tomándose la decisión analítica de conservarlos al representar *heavy users* legítimos.
4. **Ingeniería de Características y Segmentación:**
   * **`grupo_uso`:** Clasificación en *Bajo uso*, *Uso medio* y *Alto uso* según umbrales de llamadas y mensajes.
   * **`grupo_edad`:** Categorización en *Joven*, *Adulto* y *Adulto Mayor*.
5. **Visualización de Datos:** Gráficos de distribución (`countplot` con Seaborn/Matplotlib) para analizar el volumen de clientes por segmento.
6. **Insight Ejecutivo:** Elaboración de conclusiones accionables y recomendaciones estratégicas para stakeholders.
