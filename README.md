# Alice Springs and Yulara PV forecasting data guide

This repository documents the two Desert Knowledge Australia Solar Centre (DKA Solar Centre) data extracts used in a photovoltaic power forecasting study. It does **not** redistribute the original CSV files. Download the data from the provider's pages, subject to its [terms and conditions](https://dkasolarcentre.com.au/download/terms-conditions), and use the source file identifiers and study periods below to reproduce the data selection.

| Study dataset | Provider location and source identifier | Study period, inclusive | Resolution | Rows in the supplied CSV within the study period |
| --- | --- | --- | --- | ---: |
| Alice Springs | DKASC, `96-Site_DKA-MasterMeter1.csv` | 2017-01-01 to 2017-03-31 | 5 minutes | 25,920 |
| Yulara | Yulara Solar System, `3050-Site_Total_Site-PV_Generation.csv` | 2019-10-01 to 2019-11-30 | nominally 5 minutes | 17,555 |

The Alice Springs file is a **site master-meter** series; the Yulara file is labeled **total-site PV generation**. Those source identifiers are not interchangeable. The CSV files do not explicitly state a timestamp time zone, so this guide does not assign one.

## Official access

The original datasets can be obtained from the DKA Solar Centre (https://dkasolarcentre.com.au/download) subject to its terms.

- [DKASC Alice Springs data download](https://dkasolarcentre.com.au/download?location=alice-springs)
- [Yulara Solar System data download](https://dkasolarcentre.com.au/download?location=yulara)
- [DKA Solar Centre data glossary](https://dkasolarcentre.com.au/glossary)
- [Provider notes on the data](https://dkasolarcentre.com.au/download/notes-on-the-data)

On the provider's download pages, select the indicated source and date range. Access may require agreeing to the provider's terms and supplying the information requested by its download form. Cite DKA Solar Centre as the data source in any publication.

## Variables used in the study

The prediction target in both files is `Active_Power`. Historical target values are also used as input. The study's training-set feature selection retained these meteorological columns:

| Dataset | Retained meteorological inputs |
| --- | --- |
| Alice Springs | `Global_Horizontal_Radiation`, `Radiation_Global_Tilted`, `Weather_Temperature_Celsius`, `Diffuse_Horizontal_Radiation` |
| Yulara | `Global_Horizontal_Radiation`, `Pyranometer_1`, `Temperature_Probe_1`, `Temperature_Probe_2` |

`Active_Power` is AC active power in kW according to the provider's glossary. Solar irradiance is commonly reported in W/m² and temperature in °C; check the provider's source-specific metadata before assigning units to `Pyranometer_1` or the temperature-probe channels. See [DATA_DICTIONARY.md](DATA_DICTIONARY.md) for all columns in the supplied files.

## Coverage and missing values

These counts describe the supplied raw CSV rows in the stated study windows, **before** imputation, feature selection, normalization, or supervised-window construction.

- Alice Springs: 25,920 rows at uninterrupted five-minute timestamps. `Wind_Speed` is blank in every row in this window; `Radiation_Global_Tilted` has 2 blank cells.
- Yulara: 17,555 rows versus 17,568 possible five-minute timestamps, so 13 timestamps are absent. `Active_Power` has 516 blank cells; each of the 11 weather channels has 2,131 blank cells. These channel-level counts should not be interpreted as 11 separate groups of missing timestamps.

The manuscript reports 25,908 and 17,027 supervised samples, respectively, after applying its 12-observation input window and validity rules. These are **not** the raw row counts shown above. The paper's chronological split and preprocessing procedure, rather than this repository, define the evaluated samples.

## Redistribution and provenance

The provided source files are roughly 196 MB and 177 MB and contain many more than 5,000 cells. The [provider's terms](https://dkasolarcentre.com.au/download/terms-conditions) limit unaltered redistribution of DKASC Alice Springs data to 5,000 cells without formal consent. No permission to mirror these files is asserted here. Do not treat this repository as a source of raw data or as a grant of a data license; obtain the CSVs directly from DKA Solar Centre and follow its current terms.

