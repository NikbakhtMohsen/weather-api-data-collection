# Weather API Data Collection

A Python notebook for combining location information with current weather and saving the results as structured datasets.

[Open in Google Colab](https://colab.research.google.com/github/NikbakhtMohsen/weather-api-data-collection/blob/main/notebooks/weather_api_data_collection.ipynb)

## Features

- Look up addresses from latitude and longitude with LocationIQ.
- Collect current weather from OpenWeather.
- Normalise JSON replies and merge records with pandas.
- Save and verify SQLite tables.
- Export CSV, XLS and XLSX files.
- Package results in a downloadable ZIP.
- Collect additional attractions and five Iranian cities: Tehran, Isfahan, Shiraz, Tabriz and Mashhad.

## Run in Google Colab

1. Open the notebook using the link above.
2. Add `LOCATIONIQ_API_KEY` and `OPENWEATHER_API_KEY` in Colab's Secrets panel and enable notebook access.
3. Run the cells from top to bottom.
4. Download the final ZIP to keep the collected results.

Working API accounts are required. Request limits and key activation depend on the providers.

Google Drive is optional. If `/content/drive/MyDrive/Weather API` exists, the notebook saves results there. Otherwise, it uses temporary Colab storage. An existing `world_locations.csv` in that Drive folder is used as input; otherwise, the included 11-location coordinate sample is used.

## Files

| File | Purpose |
| --- | --- |
| `notebooks/weather_api_data_collection.ipynb` | Data collection and export pipeline |
| `requirements.txt` | Python dependencies alongside Colab's built-in tools |
| `.gitignore` | Excludes credentials, caches and generated files |

## Outputs

Each run creates a separate timestamped folder under `weather_data_outputs/`. The notebook writes location and weather tables, CSV/XLS/XLSX exports, a SQLite database, a collection manifest and a ZIP archive.

The combined attractions dataset includes locations in Europe, the USA and Iran. Five Iranian cities are also saved in a separate table.

## Data notes and verification

The saved collection from 22 October 2026 contained 11 initial locations, 15 rows after adding attractions and five Iranian cities. Its stored CSV, Excel and SQLite outputs were checked. The full 17-cell pipeline was also checked with simulated API replies, including missing rainfall and safe handling of connection and authentication errors.

A fresh run retrieves current observations, so weather values change over time. Temperature is in degrees Celsius and wind speed is in metres per second. Missing rainfall is left blank. The `County` column contains OpenWeather's locality name rather than a verified administrative county.

Execution outputs are cleared in the repository copy. Credentials and generated data exports are not included.

## Data providers

- [LocationIQ](https://locationiq.com/) and [attribution requirements](https://locationiq.com/attribution)
- [OpenStreetMap contributors](https://www.openstreetmap.org/copyright)
- [OpenWeather](https://openweathermap.org/)
