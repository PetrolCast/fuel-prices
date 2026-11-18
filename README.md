---
license: cc-by-4.0
pretty_name: PetrolCast fuel prices
language: [en]
tags: [fuel-prices, petrol, gasoline, diesel, lpg, energy, prices, time-series]
size_categories: [100K<n<1M]
configs:
- config_name: fuel_prices
  data_files: data/fuel_prices.csv
  default: true
- config_name: world_bank_pump_prices
  data_files: data/world_bank_pump_prices.csv
---

# PetrolCast fuel prices

Official retail fuel prices (petrol, diesel, LPG, heating oil) for 35 countries, from government publishers whose licences allow republishing, in one table with the tax split where the publisher gives it. Data through 2026-11-12. Compiled by [PetrolCast](https://petrolcast.com), where each country's prices, history and the official source of every figure are shown.

## Files

- `data/fuel_prices.csv`: 127,895 prices. One row per date, country, region and fuel.
- `data/world_bank_pump_prices.csv`: 1,249 rows. Pump prices in US dollars a litre for 55 countries, from the World Bank's archive of the GIZ mid-November survey, 1991 to 2016.
- `data/countries.csv`: country names and currencies.
- `data/sources.csv`: each publisher, its licence, its address and the credit it asks for.

## Columns of fuel_prices.csv

| Column | Meaning |
|---|---|
| date | The date the price applies to (survey date or effective date), YYYY-MM-DD |
| country_code | ISO 3166-1 alpha-2 |
| region | `national`, or a sub-national region where the publisher gives one (US: `padd1` to `padd5`) |
| fuel | `petrol`, `petrol_premium`, `diesel`, `lpg`, `heating_oil` (grades below) |
| price | Price per unit, taxes included |
| currency | ISO 4217, as quoted at the pump |
| unit | `L` (litre) |
| price_excl_tax | Price before excise duty and VAT, where published |
| excise_duty | Excise duty per unit, where published |
| other_levies | Other levies per unit, where published (New Zealand: ETS and ACC levies) |
| vat | VAT or GST per unit, where published |
| source | Publisher, see `sources.csv` |

A publisher sometimes corrects a figure after publishing it. This file holds the figures in force; [petrolcast.com/corrections](https://petrolcast.com/corrections) lists the changes.

## Sources and grades

| Source | Countries | Rows | From | To | Grades |
|---|---|---|---|---|---|
| U.S. Energy Information Administration | 1 | 13,740 | 2004-12-06 | 2026-11-09 | petrol: regular gasoline, all formulations; diesel: No. 2 on-highway diesel. National and the five PADD regions. Published in US dollars a gallon, here per litre (1 gallon = 3.785411784 litres). |
| European Commission Weekly Oil Bulletin | 27 | 104,947 | 2005-01-03 | 2026-11-09 | petrol: Euro-super 95; diesel: automotive gas oil; lpg: automotive LPG; heating_oil: heating gas oil. Taxes included, in the currency quoted at the pump; heating oil published per 1,000 litres, here per litre. |
| UK Department for Energy Security and Net Zero, weekly road fuel prices | 1 | 2,446 | 2003-06-09 | 2026-11-09 | petrol: ultra low sulphur unleaded petrol (ULSP); diesel: ultra low sulphur diesel (ULSD). Published in pence a litre, here in pounds. |
| Statistics Canada, table 18-10-0001-01 (monthly retail gasoline prices) | 1 | 249 | 2006-01-31 | 2026-09-30 | petrol: regular unleaded at self-service stations, national average. Published in cents a litre, here in dollars. |
| Malaysia Ministry of Finance weekly fuel prices (data.gov.my) | 1 | 1,461 | 2017-03-30 | 2026-11-12 | petrol: RON95, unsubsidised price; petrol_premium: RON97; diesel: Peninsular Malaysia. |
| New Zealand Ministry of Business, Innovation and Employment, weekly fuel price monitoring | 1 | 3,531 | 2004-04-23 | 2026-11-06 | petrol: regular 91; petrol_premium: 95; diesel. Published in cents a litre, here in dollars. |
| SingStat, average retail prices of selected consumer items (monthly) | 1 | 423 | 2015-01-01 | 2026-09-01 | petrol: 95 octane; petrol_premium: 98 octane; diesel. Monthly averages dated the first of the month (SingStat: indicative average transaction prices). |
| Statistics Norway (SSB), prices on engine fuel (monthly) | 1 | 964 | 1986-08-01 | 2026-09-01 | petrol: unleaded 95; diesel: road (dutiable) diesel. Monthly averages dated the first of the month, taxes included. |
| Australian Petroleum Statistics (DCCEEW), Australian fuel prices (quarterly) | 1 | 134 | 2010-01-01 | 2026-07-01 | petrol: regular unleaded 91; diesel. National quarterly averages dated the first day of the quarter. Published in cents a litre, here in dollars. |

## Licence and credit

The compilation and this documentation are by PetrolCast under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Each row keeps its publisher's licence, and reuse must credit the publisher as below. Changes made: units converted to a litre and to the main currency unit as noted above, rows put into one table; no figure is altered otherwise.

- Source: U.S. Energy Information Administration (EIA). Public domain.
- Source: European Commission, Weekly Oil Bulletin. Reproduction is authorised provided the source is acknowledged.
- Source: Department for Energy Security and Net Zero, weekly road fuel prices. Contains public sector information licensed under the Open Government Licence v3.0.
- Source: Statistics Canada, Table 18-10-0001-01, monthly average retail prices for gasoline. Statistics Canada Open Licence. This does not constitute an endorsement by Statistics Canada of this product.
- Source: Ministry of Finance Malaysia, via data.gov.my. CC BY 4.0.
- Source: Ministry of Business, Innovation and Employment (MBIE), New Zealand, weekly fuel price monitoring. Creative Commons Attribution licence, Crown copyright.
- Contains information from Average Retail Prices Of Selected Consumer Items, Monthly (M213761) from SingStat, made available under the terms of the Singapore Open Data Licence version 1.0 (https://data.gov.sg/open-data-licence).
- Source: Statistics Norway (SSB), table 09654, www.ssb.no. Licensed under CC BY 4.0 (https://creativecommons.org/licenses/by/4.0/).
- Source: Australian Petroleum Statistics, Commonwealth of Australia (Department of Climate Change, Energy, the Environment and Water). Licensed under CC BY 4.0 (https://creativecommons.org/licenses/by/4.0/).
- Source: World Bank, World Development Indicators archive (pump price for gasoline and diesel, from the GIZ International Fuel Prices survey). CC BY 4.0.

Pakistan, India and other countries shown on petrolcast.com are not included: their publishers state no licence that allows the tables to be redistributed.

## Citation

PetrolCast (2026). PetrolCast fuel prices [Data set]. https://petrolcast.com

## Contact

hello@petrolcast.com
