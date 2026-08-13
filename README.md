# Validation of Climatological Linke Turbidity Against Ground-Measured Irradiance

Solar resource / atmospheric physics research project using the DLR Eye2sky station network (station OLUOL, Oldenburg).

## Motivation
PV yield and solar resource models often rely on climatological (long-term average) turbidity databases when real-time ground measurements aren't available. This project checks how accurate that assumption actually is, using a full year of high-resolution ground irradiance data as ground truth.

## What I did
- Processed one year of 1-minute-resolution DNI/GHI/DHI irradiance measurements (525,600 timestamps) using Python (`pandas`, `pvlib`)
- Implemented the Ineichen–Perez (2002) atmospheric turbidity retrieval algorithm, including clear-sky detection and air-mass modelling
- Diagnosed and removed sun-tracker sensor artifacts through physical plausibility checks to clean the dataset
- Cross-validated retrieved turbidity against station clear-sky reference data and CAMS reanalysis aerosol optical depth data

## Key results
- Turbidity retrieval algorithm verified against station clear-sky data with **≈2.7% median error**
- Identified a **systematic ~24% overestimation** in the climatological turbidity database relative to ground-measured values
- Found a clear **seasonal pattern** in this overestimation and cross-validated extreme events against CAMS data

## Tools
Python · pandas · pvlib · NumPy · Matplotlib

## Notes
Raw irradiance data is excluded from this repo due to size/licensing (DLR Eye2sky network). Scripts assume data is loaded in the same format as the Eye2sky station output.
