Análisis ConnectaTel 📊
🎯 Objetivo del proyecto
Como analista de datos, el objetivo de este proyecto es evaluar el comportamiento de los clientes de ConnectaTel, una empresa de telecomunicaciones en Latinoamérica, utilizando información registrada hasta el año 2024. A través de la exploración, limpieza y análisis de los datos, se busca construir un perfil estadístico de los clientes, detectar comportamientos atípicos en el uso del servicio y crear segmentos según edad y nivel de consumo. Todo esto servirá para identificar patrones que permitan diseñar estrategias de retención y sugerir mejoras en los planes ofrecidos.

📁 Datasets utilizados
El análisis se construyó atravez de tres fuentes de datos principales que fueron integradas en el estudio:

Planes: Contiene la información de las tarifas actuales, los precios, los minutos y gigabytes incluidos, así como el costo por consumos extra.

Usuarios de Latam: Reúne la información de identificación de los clientes mediante su código de usuario, nombre, apellido, edad, ciudad, fecha de registro, tipo de plan y fecha de baja si corresponde.

Uso: Detalla el uso real del servicio registrando cada transacción por su identificador, el código de usuario, el tipo de evento, la fecha, la duración de la llamada o la longitud del mensaje.

🔍 Etapas del análisis
El cuaderno de trabajo está organizado en una secuencia de pasos lógicos para estraer valor de la información:

Carga y exploración: Lectura de los tres conjuntos de datos y revisión inicial de su estructura mediante funciones básicas para verificar los primeros registros, dimensiones y tipos de datos.

Identificación de problemas de calidad de datos: Revisión de valores nulos y su proporción por columna. También se realiza la detección de valores inválidos o centinelas como el número -999 en la edad y el signo de interrogación en la ciudad, junto con la revisión de fechas fuera de rango como los registros del año 2026.

Limpieza básica de datos: Corrección de los valores centinela reemplazando el valor negativo por la mediana de la edad y los signos de interrogación por valores nulos en la ciudad. Las fechas imposibles se marcan como nulas. Además, se verifica que las ausencias en duración y longitud son de tipo faltantes al azar y dependen del tipo de servicio, por lo que se toma la desición de dejarlas como nulas por su naturaleza estructural.

Estadísticas resumidas de uso por usuario: Agregación de la tabla de uso por identificador de usuario para calcular la cantidad de mensajes, llamadas y minutos totales, combinando esto con la tabla de clientes para construir el perfil final.

Visualización de distribuciones y outliers: Creación de histogramas y diagramas de caja para la edad y las métricas de consumo. Se identifican los valores atípicos mediante el método del rango intercuartílico y se opta por conservarlos debido a que representan comportamientos reales.

Segmentación de clientes: Clasificación de los usuarios por su nivel de uso en bajo, medio o alto, y por su edad en categorías de joven, adulto o adulto mayor, finalizando con una visualización de cómo se distribuyen en cada grupo.

Insight ejecutivo para stakeholders: Síntesis de los hallazgos en un análisis orientado al negocio, aportando recomendaciones sobre planes y estrategias de retención.

▶️ Cómo ejecutar el notebook
Para poner en marcha el proyecto, abre el archivo del cuaderno en Google Colab o en un entorno Jupyter local. Asegúrate de tener los archivos de planes, usuarios y uso disponibles en la ruta de datasets, o ajusta las líneas de código si los ubicas en otro directorio.

Ejecuta las celdas en orden, de arriba hacia abajo, usando la opción de correr todo. Si necesitas asegurarte de que todo funcione limpio desde el inicio, puedes reiniciar el entorno de ejecución antes de empezar. Las librerías necesarias son pandas, seaborn y matplotlib. Si trabajas de forma local, puedes instalarlas ejecutando el comando de instalación correspondiente en tu terminal de comandos.

🔁 Guía de reproducción
El cuaderno es reproducible de principio a fin, lo que significa que cada celda depende únicamente de las anteriores sin requerir pasos manuales fuera del propio código, a excepción de las interpretaciones escritas. Si el entorno se reinicia o se pierde alguna variable mostrando un error de nombre no definido, basta con volver a ejecutar el archivo desde la primera celda de carga de datos. Ten en cuenta que los resultados de segmentación y las gráficas dependen del perfil de usuario construido previamente, por lo que esa estructura debe generarse antes de pasar a las etapas finales de análisis.
