# Telecom X — exploratory customer churn analysis

[Español](README.md) · [Notebook](telecomx_datos.ipynb)

A data analysis exercise based on Alura's Telecom X challenge. It explores differences between records with and without service cancellation and practices preparing data for analysis.

## Notebook workflow

- Downloads a public JSON file from Alura.
- Flattens `customer`, `phone`, `internet` and `account` objects.
- Normalizes text and converts `Charges.Total` to numeric values.
- Fills missing total charges with zero and excludes empty `Churn` labels.
- Simplifies service categories, counts duplicates and calculates `Cuentas_Diarias`.
- Produces descriptive statistics, counts, bar charts and box plots.

Charts compare cancellation with contract, payment method, gender, tenure and charges. They describe associations in the dataset, not causes or a measured improvement in customer retention.

## Data and stack

Source: [Alura challenge TelecomX_Data.json](https://raw.githubusercontent.com/alura-cursos/challenge2-data-science-LATAM/refs/heads/main/TelecomX_Data.json).

Python, pandas, NumPy, Matplotlib, seaborn and a Jupyter environment. The source is a file hosted on GitHub, not a production customer API. Its branch-based URL can change.

## Run

Open [the notebook in Google Colab](https://colab.research.google.com/github/fabrizzio2901/TelecomX-Datos/blob/main/telecomx_datos.ipynb), connect a runtime and execute cells in order from a clean session.

For local execution:

```bash
git clone https://github.com/fabrizzio2901/TelecomX-Datos.git
cd TelecomX-Datos
python -m venv .venv
```

Activate the environment:

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

Internet access is needed to download the JSON. No credentials are required.

## Example interpretation

Run all cells and compare the `tenure` distribution for `Churn = yes` and `Churn = no`. Then inspect counts by `Contract`. Comparing risks across differently sized groups requires within-group rates; counts alone are insufficient.

## Status and limitations

The repository contains a notebook with saved outputs. There is no deployed application, model training or pinned dependency file.

Filling missing `Charges.Total` values with zero is an exercise-specific decision whose suitability should be assessed before reuse. The notebook counts duplicates but does not remove them.

It does not export `datos_tratados.csv`. A downstream project requiring that file needs a documented, verifiable export step. Results describe the exercise, not outcomes for a real client.

## Credits

Challenge and data: Alura. This repository contains the exercise published on [fabrizzio2901's profile](https://github.com/fabrizzio2901).

## Verified result

On September 11, 2026, all 30 nonempty code cells ran in order in a clean Python process with pandas 3.0.5, Matplotlib 3.11.2 and seaborn 0.13.2. The workflow transformed 7,267 input records into 7,043 records and 22 columns, with 5,174 `no` and 1,869 `yes` churn labels. These are reproduced educational-dataset counts, not business-impact indicators. Colab and JupyterLab interfaces were not tested.

## My contribution

I contributed to implementing the data preparation and analysis notebook. This exercise complements my full-stack development work; its scope is data analysis in Python.
