# Spotify Chart Regression

**Course:** DATA 603 Statistical Modeling with Data, University of Calgary (December 2023) · **Team:** Riki Enquist, Luke Bramfield, Ethan Burke
**Report source:** [SpotifyRegressionProject.Rmd](SpotifyRegressionProject.Rmd)

## Question
Which song and release characteristics predict how high a 2023 song ranks on the Spotify charts? The question is framed for a record label deciding how to release and promote music.

## Approach
1. **Full model:** fit a multiple regression with artist count, release month, playlist and chart presence on other platforms, BPM, key, mode, and audio features such as danceability, valence and energy.
2. **Model selection, three ways:**
   - manual review of individual t-tests and a partial F-test
   - stepwise selection in both directions (olsrr)
   - all-possible-regressions, compared on adjusted R², Mallows' Cp, BIC and RMSE (leaps)
3. **Model refinement:** tested interaction and higher-order terms, and checked multicollinearity with VIF.
4. **Assumption checks:** linearity, constant variance (Breusch-Pagan), normality (Shapiro-Wilk, Q-Q plots) and outliers. A square-root transform of the response fixed the violations.

## Results
- Final model: adjusted R² of 0.474, so it explains about 47% of the variation in chart position.
- Significant predictors were Deezer playlist presence, release month and valence (how upbeat a song sounds), plus two interaction terms.
- Takeaways for a label: release later in the year, favour upbeat tracks, and be cautious with many-artist features.
