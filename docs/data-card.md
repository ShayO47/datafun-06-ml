# Data Card: CO₂ and Economic Data

## Dataset

This project uses `data/raw/owid-co2-data-subset.csv`, a subset
of the [Our World in Data CO₂ and greenhouse gas emissions
dataset](https://github.com/owid/co2-data).

## Grain

Each row represents **one country or entity in one year**.

## Relevant Fields

| Field            | Description                     |
| ---------------- | ------------------------------- |
| `country`        | Country or entity name          |
| `year`           | Observation year                |
| `population`     | Population for the observation  |
| `gdp`            | Gross domestic product          |
| `co2`            | Annual CO₂ emissions            |
| `co2_per_capita` | Annual CO₂ emissions per person |

## Derived Field

| Field            | Calculation        | Purpose          |
| ---------------- | ------------------ | ---------------- |
| `gdp_per_capita` | `gdp / population` | GDP per person.  |

## Preparation for Modeling

The original dataset contained 350 rows. The project created
`gdp_per_capita` and then removed rows missing either GDP per
capita or CO₂ emissions per capita. This resulted in 308 complete
rows for modeling.

## Use and Limitations

This dataset supports exploration of relationships between
economic activity and emissions. It should not be used to claim
that GDP alone causes CO₂ emissions. Many other factors may
affect emissions, including energy sources, industrial activity,
technology, and public policy.
