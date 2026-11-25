# MLB Power Hitting and Plate Discipline

**Course:** DATA 602, University of Calgary (October 2023) · **Author:** Riki Enquist
**Analysis:** [MLBPlayerAnalysis.Rmd](MLBPlayerAnalysis.Rmd)

## Question
What drives run production in MLB: hitting for power, plate discipline, or getting on base?

## Data
2022 MLB batting statistics for every player with at least 81 games. Traded players are counted once, using their combined season totals. Counting stats are normalized per at-bat or per plate appearance so players can be compared fairly.

## Approach
1. **Power:** split players at the league median of home runs per at-bat. Then compared runs per at-bat between the two groups using bootstrap resampling (10,000 samples), a one-sample t-test and a two-sample t-test.
2. **Discipline:** chi-squared tests and correlations between walks per plate appearance, age, runs per plate appearance and on-base percentage.
3. **Regression:** a simple linear regression of runs per plate appearance on on-base percentage, with residual diagnostics.
4. **Out-of-sample check:** predicted 2022 and 2023 run totals for Vladimir Guerrero Jr. and Seiya Suzuki, then compared them with their actual totals.

## Results
- Above-median power hitters score significantly more runs per at-bat.
- On-base percentage has the strongest relationship with run production. The fitted model is: runs per PA = 0.006 + 0.350 × OBP.
- Walk rate is positively linked to run production, while age shows no clear relationship.
- Bottom line for a front office: find hitters who get on base.
