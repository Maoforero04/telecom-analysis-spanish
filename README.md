Análisis de Segmentación de Clientes — ConnectaTel
🎯 Objetivo del proyecto

ConnectaTel busca entender mejor a su base de clientes en Latinoamérica para optimizar su oferta de planes (Básico y Premium). Este proyecto analiza los datos de usuarios y su comportamiento de uso (llamadas y mensajes) durante el 2024 con el fin de:

Evaluar y corregir la calidad de los datos disponibles.
Construir un resumen del comportamiento de uso por usuario.
Segmentar a los clientes según su edad y nivel de uso.
Identificar patrones y valores atípicos (outliers) relevantes para el negocio.
Traducir los hallazgos en conclusiones accionables: qué segmentos son más valiosos, qué oportunidades comerciales existen y qué cambios se recomiendan en los planes actuales o en la creación de nuevos planes.
📊 Datasets utilizados

El proyecto integra tres datasets:

users_latam.csv (4,000 usuarios) — Información demográfica y de suscripción de cada usuario: user_id, first_name, last_name, age, city, reg_date, plan, churn_date.
usage.csv (40,000 registros) — Registro de eventos de uso (llamadas y mensajes) durante 2024: id, user_id, type (call / text), date, duration (minutos, para llamadas), length (caracteres, para mensajes).
plans.csv — Catálogo de los planes disponibles y sus condiciones: plan_name, messages_included, gb_per_month, minutes_included, usd_monthly_pay, usd_per_gb, usd_per_message, usd_per_minute.
🔍 Etapas del análisis

Paso 1: Cargar y explorar

Exploración de la estructura de los tres datasets (dimensiones, tipos de datos, primeras filas).

Paso 2: Identificación de problemas de calidad de datos

Revisión de valores nulos.
Detección de valores inválidos y sentinels (ej. "?" en city).
Revisión y estandarización de fechas (reg_date, churn_date, date).

Paso 3: Limpieza básica de datos

Corrección de sentinels y fechas imposibles.

Paso 4: Summary statistics de uso por usuario

Agrupación de usage.csv por usuario para construir el comportamiento de uso.
Resumen estadístico por usuario durante el 2024 (cantidad de mensajes, cantidad de llamadas, minutos totales de llamada, entre otros).

Paso 5: Visualización de distribuciones (uso y clientes) y outliers

Visualización de distribuciones: histogramas para age, cant_mensajes, cant_llamadas y total_minutos_llamada.
Identificación de outliers: boxplots para las mismas columnas (age, cant_mensajes, cant_llamadas, total_minutos_llamada).

Paso 6: Segmentación de clientes

Por uso: clasificación de cada usuario en Bajo uso / Uso medio / Alto uso, según su cantidad de llamadas y mensajes.
Por edad: clasificación de cada usuario en un grupo etario.
Visualización: gráficos de barra mostrando la distribución de usuarios según grupo_uso y grupo_edad.

Paso 7: Insight ejecutivo para stakeholders

Traducción de los hallazgos del análisis en conclusiones accionables para el negocio, enfocadas en segmentación, patrones de uso y oportunidades comerciales.

▶️ Cómo ejecutar el notebook
Google Colab (recomendado)
Abre Google Colab.
Ve a Archivo > Abrir notebook > GitHub, pega la URL de este repositorio y selecciona el notebook (.ipynb).
Sube los tres datasets (users_latam.csv, usage.csv, plans.csv) a la sesión de Colab desde el panel de archivos (ícono de carpeta a la izquierda), o móntalos desde Google Drive si prefieres persistencia entre sesiones.
Ejecuta las celdas en orden con Entorno de ejecución > Ejecutar todas.

🔁 Guía de reproducción
Coloca los tres archivos fuente (users_latam.csv, usage.csv, plans.csv) en la misma carpeta que el notebook, o ajusta las rutas de carga según corresponda.
Ejecuta el notebook en orden — cada paso depende del anterior (la limpieza precede al resumen de uso, que a su vez precede a la segmentación y las visualizaciones).
El Paso 3 corrige sentinels y fechas inválidas: verifica que no queden errores antes de continuar a los pasos siguientes.
Las columnas grupo_uso y grupo_edad se generan automáticamente durante la ejecución del Paso 6 — no es necesario crearlas manualmente.
Las conclusiones e insights ejecutivos del Paso 7 se encuentran documentados al final del notebook.
