# Telecom X — análisis exploratorio de cancelación de clientes

[English](README.en.md) · [Notebook](telecomx_datos.ipynb)

Ejercicio de análisis de datos basado en el desafío Telecom X de Alura. Explora diferencias entre registros con y sin cancelación de servicio y practica la preparación de datos para su análisis.

## Qué hace el notebook

- Descarga un archivo JSON público de Alura.
- Aplana las estructuras `customer`, `phone`, `internet` y `account`.
- Normaliza textos y convierte `Charges.Total` a valores numéricos.
- Rellena cargos totales vacíos con cero y excluye registros con `Churn` vacío.
- Simplifica categorías de servicios, cuenta duplicados y calcula `Cuentas_Diarias`.
- Genera estadísticas descriptivas, conteos, gráficos de barras y diagramas de caja.

Los gráficos comparan cancelación con contrato, método de pago, género, antigüedad y cargos. Describen asociaciones dentro del conjunto analizado; no demuestran causas ni una mejora real de retención.

## Datos y tecnologías

Fuente: [TelecomX_Data.json del desafío de Alura](https://raw.githubusercontent.com/alura-cursos/challenge2-data-science-LATAM/refs/heads/main/TelecomX_Data.json).

Python, pandas, NumPy, Matplotlib, seaborn y un entorno Jupyter. La fuente es un archivo alojado en GitHub, no una API de clientes en producción. La URL apunta a una rama que puede cambiar.

## Ejecutar

Opción sencilla: abre [el notebook en Google Colab](https://colab.research.google.com/github/fabrizzio2901/TelecomX-Datos/blob/main/telecomx_datos.ipynb), conecta un entorno y ejecuta las celdas en orden desde un entorno limpio.

Para trabajar localmente:

```bash
git clone https://github.com/fabrizzio2901/TelecomX-Datos.git
cd TelecomX-Datos
python -m venv .venv
```

Activa el entorno:

```powershell
# Windows PowerShell
.\.venv\Scripts\Activate.ps1
```

```bash
# macOS / Linux
source .venv/bin/activate
```

```bash
python -m pip install pandas numpy matplotlib seaborn jupyterlab
python -m jupyterlab telecomx_datos.ipynb
```

Se necesita acceso a Internet para descargar el JSON. No se requieren credenciales.

## Ejemplo de lectura

Ejecuta todas las celdas y compara la distribución de `tenure` entre `Churn = yes` y `Churn = no`. Después revisa los conteos por `Contract`. Para comparar riesgos entre categorías con tamaños diferentes hace falta calcular tasas dentro de cada grupo; los conteos por sí solos no bastan.

## Estado y límites

El repositorio incluye el notebook y sus salidas guardadas. No contiene una aplicación desplegada, entrenamiento de modelos ni un archivo de dependencias con versiones fijadas.

La imputación de `Charges.Total` con cero es una decisión del ejercicio y requiere revisar su pertinencia antes de reutilizar el análisis. El notebook cuenta duplicados, pero no ejecuta una eliminación de duplicados.

No exporta `datos_tratados.csv`: cualquier proyecto posterior que dependa de ese archivo necesita un paso adicional de exportación documentado y verificable. Los resultados pertenecen al ejercicio; no son métricas de un cliente real.

## Créditos

Desafío y datos: Alura. Este repositorio contiene el desarrollo del ejercicio publicado en el perfil de [fabrizzio2901](https://github.com/fabrizzio2901).

## Resultado verificado

El 11 de septiembre de 2026 se ejecutaron en orden las 30 celdas de código no vacías, en un proceso Python limpio con pandas 3.0.5, Matplotlib 3.11.2 y seaborn 0.13.2. El flujo pasó de 7,267 registros de entrada a 7,043 registros y 22 columnas; `Churn` quedó con 5,174 valores `no` y 1,869 `yes`. Son conteos reproducidos del conjunto educativo, no indicadores de impacto comercial. No se probó la interfaz de Colab ni de JupyterLab.

## Mi participación

Participé en la implementación del notebook de preparación y análisis de datos. Este ejercicio complementa mi trabajo de desarrollo full stack; su alcance es análisis de datos en Python.
