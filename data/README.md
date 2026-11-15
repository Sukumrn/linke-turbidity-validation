# Data directory

The OLUOL Eye2Sky NetCDF station dataset is not committed to this repository because it is subject to the original provider's access and licensing conditions.

If you have permission to use the dataset, place the file here with this exact name:

```
data/OLUOL.cleaned.nc
```

The Linke turbidity notebooks expect this relative path. Do not commit restricted station data, API credentials, or personal configuration files.

Some exploratory cells retrieve CAMS reanalysis data through the Copernicus Climate Data Store API. Configure your CDS API credentials locally before running those cells. Downloaded CAMS files are excluded from version control by the repository's `.gitignore`.
