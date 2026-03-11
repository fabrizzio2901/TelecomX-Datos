# TelecomX-Datos

# Análisis de Evasión de Clientes (Churn) - Telecom X

## Propósito del Proyecto
Este proyecto tiene como objetivo analizar la base de datos de la empresa de telecomunicaciones Telecom X para descubrir los motivos principales por los que los clientes cancelan su servicio (fenómeno conocido como *Churn*). 

A través de un proceso de limpieza de datos (ETL) y un Análisis Exploratorio (EDA) en Python, buscamos transformar datos crudos en información estratégica. El resultado final ayuda a identificar patrones de comportamiento y ofrece recomendaciones claras para retener a más usuarios.

## Estructura del Proyecto
El análisis está organizado de manera sencilla para facilitar su lectura y ejecución:

* **`telecomx_datos.ipynb`**: Es el archivo principal del proyecto. Un Jupyter Notebook diseñado para ejecutarse en Google Colab. Contiene todo el código Python paso a paso, desde la descarga de los datos hasta las gráficas finales.
* **Fuente de Datos**: Los datos no están guardados localmente, sino que el código se conecta directamente a una API pública para descargar la información en formato JSON, asegurando que siempre se trabaje con la versión correcta.

## Insights y Visualizaciones Clave
Durante el análisis, utilizamos librerías como `seaborn` y `matplotlib` para hacer hablar a los números. Algunos de los descubrimientos más importantes fueron:

1. **El peligro del contrato mensual:** Mediante gráficos de barras, confirmamos que los clientes con contratos "mes a mes" (Month-to-month) son los que más abandonan a la empresa.
2. **Los primeros meses son críticos:** Utilizando Diagramas de Caja (Boxplots), descubrimos visualmente que la gran mayoría de las cancelaciones ocurren en los primeros meses de antigüedad. Si el cliente supera esa barrera, es muy probable que se quede.
3. **El impacto del precio:** Los mismos diagramas de caja nos revelaron que los clientes que pagan las mensualidades más caras tienen una tendencia mucho mayor a cancelar el servicio.

> Nota para el lector: Dentro del notebook encontrarás los gráficos detallados que respaldan cada una de estas conclusiones.

## Instrucciones para Ejecutar el Notebook
Replicar este análisis es muy sencillo. Solo necesitas seguir estos pasos:

1. Descarga el archivo `telecomx_datos.ipynb` de este repositorio.
2. Entra a Google Colab y sube el archivo.
3. No necesitas descargar ninguna base de datos manual. El primer bloque de código se encarga de extraer la información automáticamente desde la API.
4. Las librerías utilizadas (`pandas`, `matplotlib`, `seaborn` y `numpy`) ya vienen instaladas por defecto en Google Colab.
5. Ve al menú superior, selecciona "Entorno de ejecución" y haz clic en "Ejecutar todas". 

---
**Autor:** Luis Fabrizzio Ramirez Romero
