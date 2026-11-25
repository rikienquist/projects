# Canadian Banking Industry Analysis

**Course:** DATA 604 Working with Data at Scale, University of Calgary (December 2023) · **Team:** Luke Bramfield, Ethan Burke, Riki Enquist, Niza Ngwira
**Report:** [Final Report (PDF)](Data%20604%20-%20Analysis%20of%20the%20Canadian%20Banking%20Industry%20-%20Final%20Report.pdf)

This team project looked at Canada's Big 5 banks from four angles: customer sentiment, transactions, lending conditions, and branch locations compared with demographics. **My part was the transaction analysis.** The other sections were done by my teammates and are included in the full report.

## My question
What seasonal patterns appear in Government of Canada transactions processed by the Big 5 banks, and how did COVID-19 change them?

## Data
Government Banking System transaction records from Public Services and Procurement Canada, April 2019 to September 2023.

## Approach
- Loaded the yearly files into MySQL.
- Wrote SQL to filter to the Big 5 banks by institution number, combine the years into one table, and aggregate monthly transaction counts, average amounts, and counts by transaction type and bank.
- Analyzed and visualized the results in Python.

## Findings
- **Clear seasonal cycle:** spring has fewer but larger transactions (tax settlements). Summer has more, smaller transactions (refunds and routine payments).
- **COVID-19:** deepened the seasonal low and lowered the peak, consistent with business closures and support programs such as CERB.
- **Bank mix:** RBC processes the largest share, driven by credit-card payments for government services. TD processes the fewest.
