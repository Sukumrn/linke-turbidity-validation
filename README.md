# Linke Turbidity Analysis Using Ground-Based Irradiance Measurements

A solar-meteorology project examining climatological Linke turbidity at the OLUOL station of the DLR Eye2Sky network in Oldenburg, Germany, using ground-based irradiance measurements and Python-based analysis.

## Research objective

Assess how a climatological Linke turbidity value compares with turbidity retrieved from station measurements, and examine the implications for clear-sky irradiance modelling and solar-resource assessment.

## Data

- **Station:** OLUOL, Oldenburg, Germany
- **Measurement period:** 1 April 2022 – 1 April 2023
- **Sampling:** nominal one-minute measurements
- **Variables used:** GHI, DNI, DHI, clear-sky irradiance references, solar zenith angle, and station metadata
- **Additional context:** selected Copernicus CAMS reanalysis aerosol optical depth fields

The original Eye2Sky NetCDF dataset is not redistributed here. Access and file placement instructions are in [data/README.md](data/README.md).

## Workflow

1. Inspect station metadata and measured/clear-sky irradiance variables.
2. Apply daytime, clear-sky, and air-mass quality filters.
3. Retrieve Linke turbidity using the Ineichen–Perez formulation.
4. Compare the derived time series and monthly statistics with the pvlib climatological Linke turbidity lookup.
5. Examine the effect of alternative turbidity inputs on clear-sky irradiance estimates.
6. Investigate selected high-turbidity periods using CAMS aerosol data.

## Repository contents

- `notebooks/01_linke_turbidity_exploratory.ipynb` — data inspection, retrieval workflow, and exploratory CAMS checks.
- `notebooks/02_linke_turbidity_project_analysis.ipynb` — documented methodology, comparisons, and project presentation.
- `data/README.md` — instructions for the external station dataset.
- `requirements.txt` — Python package dependencies.

## Run the notebooks

Create an environment and install the listed packages:

```bash
python -m venv .venv
source .venv/bin/activate
# On Windows: .venv\Scripts\activate
pip install -r requirements.txt
jupyter lab
```

Place the authorised `OLUOL.cleaned.nc` file in the `data/` directory before running the notebooks. CAMS retrieval cells additionally require Copernicus Climate Data Store API access and a local CDS API configuration.

## Methods and references

- Ineichen, P. & Perez, R. (2002). A new airmass independent formulation for the Linke turbidity coefficient. *Solar Energy*, 73(3), 151–157.
- Reno, M. J. & Hansen, C. W. (2016). Identification of periods of clear sky irradiance in time series of GHI measurements.
- Copernicus Atmosphere Monitoring Service (CAMS), global reanalysis (EAC4).
- pvlib Python documentation: https://pvlib-python.readthedocs.io/

## Limitations and interpretation

This repository documents an academic analysis, not a certified operational retrieval product. Derived values depend on sensor quality, clear-sky detection, solar-zenith and air-mass filters, and the comparison statistic. Numerical claims about percentage error or climatological bias should be quoted only together with the exact calculation, sample selection, and aggregation method used.

The station data are subject to the original provider's access and licensing conditions and are therefore not included.
