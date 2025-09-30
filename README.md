  # Extended U.S. Economic Indicators: GDP and Unemployment Data (1920–Present)

This repository contains extended datasets for U.S. Gross Domestic Product (GDP) and Unemployment Rates, combining official modern data with historical annual data compiled from archival sources. The goal is to provide a continuous time series starting from 1920, filling gaps where official quarterly or monthly data is unavailable prior to the late 1940s.

The datasets are unique in their manual extension using historical statistics, making them suitable for long-term economic analysis, research, or educational purposes.

## Data Sources

### Gross Domestic Product (GDP)
- **Modern Data**: Quarterly, seasonally adjusted GDP data from January 1947 to the present, sourced from the U.S. Bureau of Economic Analysis (BEA) via the Federal Reserve Bank of St. Louis (FRED).
- **Historical Extension**: Annual real GDP data for 1920–1946 manually compiled from the U.S. Census Bureau’s *Bicentennial Edition: Historical Statistics of the United States, Colonial Times to 1970*. Official GDP data prior to 1947 is not available from BEA or FRED.
- **Archive Link**: [U.S. Census Bureau Historical Statistics](https://www.census.gov/library/publications/1975/compendia/hist_stats_colonial-1970.html)

### Unemployment Rate
- **Modern Data**: Monthly unemployment rate data from January 1948 to the present, sourced from the U.S. Bureau of Labor Statistics (BLS) via the Federal Reserve Bank of St. Louis (FRED).
- **Historical Extension**: Annual unemployment data for 1920–1947 manually compiled from the U.S. Census Bureau’s *Bicentennial Edition: Historical Statistics of the United States, Colonial Times to 1970*.
- **Archive Link**: [U.S. Census Bureau Historical Statistics](https://www.census.gov/library/publications/1975/compendia/hist_stats_colonial-1970.html)

## Dataset Files

### GDP Files
- **gdp_combined_1920_2023_annual.csv**: The extended dataset combining historical annual data (1920–1946) with annual aggregates from modern sources (1947–2023). Columns include:
  - `Year`: The calendar year.
  - `GDP`: Real GDP in billions of chained dollars (or appropriate unit; adjust based on your data normalization).
  - `Source`: Indicates whether data is from "Census Historical" or "BEA/FRED".
- **gdp_since_1920_1947_annual_us_census_bureau.csv**: Historical annual GDP data specifically from the U.S. Census Bureau (1920–1947). This is the raw extension data used in the combined file.

### Unemployment Files
- **unrate_1920_1948.csv**: The extended dataset with annual unemployment rates (1920–1947) and monthly data starting from 1948. Columns include:
  - `Date`: Year or YYYY-MM format.
  - `Unemployment Rate`: Percentage of the labor force unemployed.
  - `Source`: Indicates whether data is from "Census Historical" or "BLS/FRED".
- **unrate_since_1948_mly_bls.csv**: Monthly unemployment rate data from BLS/FRED (1948–present). This is the raw modern data used in the extended file.

## Data Compilation Process
1. **Historical Data**: Manually extracted from tables in the U.S. Census Bureau’s historical compendium. For GDP, this involved aggregating or estimating annual figures where quarterly data was absent. For unemployment, annual averages were used.
2. **Modern Data**: Downloaded from FRED API or website.
3. **Merging**: Historical and modern data were aligned by year, with any necessary adjustments for consistency (e.g., chaining methods for GDP). The combined files provide a seamless time series.
4. **Notes on Limitations**:
   - Pre-1947 data is annual only; no quarterly or monthly breakdowns available.
   - Data may have methodological differences between historical and modern sources (e.g., definitions of unemployment).
   - Ensure to check for updates from official sources, as this dataset is a snapshot up to 2023.

## Usage
- **Loading in Python (Example)**:
  ```python
  import pandas as pd

  # Load combined GDP data
  gdp_df = pd.read_csv('gdp_combined_1920_2023_annual.csv')
  print(gdp_df.head())

  # Load extended unemployment data
  unrate_df = pd.read_csv('unrate_1920_1948.csv')
  print(unrate_df.head())
  ```
- These datasets can be used for time-series analysis, econometric modeling, or visualization in tools like Excel, R, or Python.

## License
This dataset is released under the [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/) license. You are free to share and adapt the data, provided you give appropriate credit to the original sources (BEA, BLS, FRED, and U.S. Census Bureau) and this repository.

## Acknowledgments
- Data compilation inspired by the need for long-term economic historical context.
- Thanks to the U.S. government agencies for providing public data.

If you use this dataset in your work, please cite it as: "Extended U.S. GDP and Unemployment Data (1920–Present), [Your GitHub Username/Repo], 2025."

For questions or contributions, open an issue or pull request in this repository.
