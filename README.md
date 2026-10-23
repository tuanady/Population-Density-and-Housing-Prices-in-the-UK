# Correlation Between Population Density and Housing Prices in the UK (2013–2023)

A data-wrangling and analysis project that explores whether rising population density is linked to rising house prices in the United Kingdom over ten years, and compares a dense urban area (**London**) with a rural one (**Pembrokeshire**, Wales).

## Key findings

| Metric (UK, 2013–2023) | Value |
|---|---|
| Pearson correlation: house price vs. population density | **0.94** |
| Average yearly population increase | ~383,800 people |
| Average yearly house-price increase | ~£8,115 |
| Price change per 100,000 additional residents | ~£2,114 |

- UK house prices and population density moved together very closely over the decade, with prices peaking in **2022**.
- **London** (≈6,100 people/km² in 2023) has far higher prices (≈£518k) than **Pembrokeshire** (≈77 people/km², ≈£245k), yet both show steady price growth.
- Correlation does not imply causation: interest rates, wages and housing supply also play a large role.

## Data sources

| File | Description |
|---|---|
| `housing_prices.csv` | Monthly UK average house prices |
| `population_data.csv` | Population by country per year (World Bank format) |
| `land_of_countries.xml` | Land area by country, used to compute density |
| `london_population.csv`, `london_prices.csv` | London population and average prices |
| `pembrokeshire_population.csv`, `pembrokeshire_prices.csv` | Pembrokeshire population and average prices |

## Methodology

1. **Load and clean:** read CSV and XML sources, filter to 2013–2023, fix types.
2. **Transform:** reshape wide → long (`melt`), parse the XML for UK land area, compute population density.
3. **Merge:** join housing prices with density by year.
4. **Analyze:** Pearson correlation, average yearly increases, price change per population unit.
5. **Visualize:** dual-axis line charts (price vs. density) for the UK, London and Pembrokeshire, plus peak-year highlights.

## Run it

```bash
pip install pandas numpy seaborn matplotlib jupyter
cd "Housing Prices and Population"
jupyter notebook data_wrangling.ipynb
```

## Tech stack

Python · pandas · NumPy · Matplotlib · Seaborn · XML (ElementTree) · Jupyter
