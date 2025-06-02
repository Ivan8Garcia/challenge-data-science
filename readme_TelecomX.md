Descripción del Proyecto Telecom X

**Propósito del Análisis:**

El objetivo principal de este proyecto es realizar un Análisis Exploratorio de Datos (AED) sobre un dataset de clientes de una empresa de telecomunicaciones. El propósito es identificar los factores clave que contribuyen a la "evasión" o "Churn" de clientes. Comprender las características y el comportamiento de los clientes que se dan de baja es crucial para desarrollar estrategias efectivas de retención de clientes y minimizar la pérdida de ingresos. El análisis busca descubrir patrones, relaciones y variables significativas que influyen en la decisión de un cliente de abandonar el servicio.

Estructura del Proyecto y Organización de los Archivos:
El proyecto se implementa en un único notebook de Google Colaboratory. La organización dentro del notebook sigue un flujo lógico de un proceso de análisis de datos:
1.  **Extracción:** Carga de los datos desde una fuente externa (URL pública con formato JSON). Se utiliza `requests` y `json` para obtener los datos y `pd.json_normalize` para aplanar la estructura anidada del JSON en un DataFrame plano de pandas.
2.  **Transformación:** Limpieza y preparación de los datos. Incluye la verificación y manejo de valores ausentes y duplicados, la inspección de valores únicos en columnas categóricas, la conversión de tipos de datos ('TotalCharges' a numérico), el mapeo de valores binarios ('Yes'/'No' a 1/0), y la creación de una nueva columna ('Daily_Charges') a partir de datos existentes.
3.  **Carga y Análisis:** Realización del análisis exploratorio de los datos limpios. Se divide en subsecciones:
    *   Análisis Descriptivo: Cálculo de estadísticas sumarias para variables numéricas.
    *   Distribución de Evasión: Visualización de la proporción de clientes con y sin Churn.
    *   Recuento de Evasión por Variables Categóricas: Análisis de la tasa de Churn por categorías (género, contrato, método de pago, servicios, etc.) utilizando tablas de contingencia y gráficos de barras.
    *   Conteo de Evasión por Variables Numéricas: Análisis de la distribución de variables numéricas (antigüedad, cargos mensuales, cargos totales) para los grupos con y sin Churn utilizando boxplots.
4.  **Informe Final:** Sección que resume los hallazgos clave, los insights obtenidos y propone recomendaciones estratégicas basadas en el análisis.

Ejemplos de Gráficos e Insights Obtenidos:
*   **Gráfico de Distribución de Churn:** Un gráfico de barras o pastel que muestra claramente que aproximadamente el 26.5% de los clientes han evadido.
*   **Gráfico de Proporción de Churn por Tipo de Contrato:** Gráfico de barras que ilustra que los clientes con contratos mensuales tienen una tasa de Churn significativamente más alta que aquellos con contratos anuales o bianuales. Insight: La duración del contrato es un fuerte predictor de Churn.
*   **Gráfico de Boxplot para Antigüedad (Tenure) por Churn:** Un boxplot que muestra que la mediana de antigüedad para los clientes que evaden es considerablemente menor que para los que no. Insight: Los clientes nuevos son más propensos a evadir.
*   **Gráfico de Proporción de Churn por Método de Pago:** Gráfico de barras que resalta que el método de pago 'Electronic check' se asocia con una tasa de Churn elevada. Insight: Investigar problemas potenciales con este método de pago.

Instrucciones para Ejecutar el Notebook:
1.  Abrir el archivo `.ipynb` en Google Colaboratory.
2.  Asegurarse de tener conexión a internet, ya que los datos se descargan desde una URL externa.
3.  Ejecutar cada celda de código secuencialmente desde el principio hasta el final.
4.  El notebook instalará automáticamente las bibliotecas necesarias si no están presentes en el entorno de Colab (aunque `pandas`, `requests`, `json`, `numpy`, `matplotlib`, `seaborn` suelen estar preinstaladas).
5.  Observar la salida de cada celda para ver los resultados del proceso de extracción, transformación y los gráficos generados durante el análisis exploratorio.
6.  Leer la sección "INFORME FINAL" al final del notebook para obtener un resumen de los hallazgos y las recomendaciones.
