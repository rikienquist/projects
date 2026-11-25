# U.S. Corn Market Analysis

**Course:** University of Calgary MDSA (Fall 2023) · Team project
**Notebook:** [CornIndustryAnalysis.ipynb](CornIndustryAnalysis.ipynb)

## Questions
1. How does weather in the Midwest (Illinois, Indiana and Iowa) affect corn yield?
2. How has the efficiency of corn production changed over time?
3. How does the price per bushel relate to corn stocks and biofuel demand?
4. How do yield and price interact, and how well can farmers hedge with futures?

## Data
- Palmer Z drought index by state, 1995–2022 (NOAA).
- Yield, plant population, stocks and price data (USDA National Agricultural Statistics Service).
- Fertilizer use and corn futures prices.

## Approach
- Cleaned and merged the multi-source data in pandas.
- Built drought heatmaps for each growing season.
- Tested correlation and significance between weather and yield, and between price, stocks and demand.
- Used ANOVA to study farmer decisions.
- Used a probability distribution of the futures basis to assess hedging risk.
