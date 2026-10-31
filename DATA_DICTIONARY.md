# Data dictionary

The tables list column names as they appear in the two supplied CSV files. Descriptions follow the column names and the [DKA Solar Centre glossary](https://dkasolarcentre.com.au/glossary). Exact sensor specifications, sign conventions, and units not expressly identified by the provider should be checked against its source metadata before analysis.

## Alice Springs master meter

| Column | Description |
| --- | --- |
| `timestamp` | Recorded observation time; no explicit time-zone field. |
| `Active_Energy_Delivered_Received` | Cumulative delivered-minus-received active energy. |
| `Current_Phase_Average` | Average phase current. |
| `Active_Power` | Active power; study target. |
| `Power_Factor_Signed` | Signed electrical power factor. |
| `Average_Voltage_Line_to_Neutral` | Mean line-to-neutral voltage. |
| `Frequency` | Electrical frequency. |
| `THD_Voltage_Average` | Average total harmonic voltage distortion. |
| `Wind_Speed` | Wind speed; entirely blank in the 2017 study window. |
| `Weather_Temperature_Celsius` | Ambient temperature. |
| `Weather_Relative_Humidity` | Relative humidity. |
| `Global_Horizontal_Radiation` | Global horizontal solar irradiance. |
| `Diffuse_Horizontal_Radiation` | Diffuse horizontal solar irradiance. |
| `Wind_Direction` | Wind direction. |
| `Radiation_Global_Tilted` | Solar irradiance measured on a tilted plane. |

## Yulara total-site PV generation

| Column | Description |
| --- | --- |
| `timestamp` | Recorded observation time; no explicit time-zone field. |
| `Active_Energy_Delivered_Received` | Cumulative delivered-minus-received active energy. |
| `Active_Power` | Active power; study target. |
| `Wind_Speed` | Wind speed. |
| `Weather_Temperature_Celsius` | Ambient temperature. |
| `Global_Horizontal_Radiation` | Global horizontal solar irradiance. |
| `Wind_Direction` | Wind direction. |
| `Weather_Daily_Rainfall` | Daily rainfall channel. |
| `Max_Wind_Speed` | Maximum wind-speed channel. |
| `Air_Pressure` | Air-pressure channel. |
| `Hail_Accumulation` | Hail-accumulation channel. |
| `Pyranometer_1` | Pyranometer sensor channel; confirm units and invalid-value codes in source metadata. |
| `Temperature_Probe_1` | Temperature-probe sensor channel; confirm location and units in source metadata. |
| `Temperature_Probe_2` | Second temperature-probe sensor channel; confirm location and units in source metadata. |

Blank-cell counts and study periods are documented in [README.md](README.md). The original files are not included in this repository.

