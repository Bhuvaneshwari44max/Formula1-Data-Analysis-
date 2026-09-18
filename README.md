F1 Descriptive Analysis: Race-Day Performance & Competitive Balance (1950–2024)

Overview

A descriptive analysis of 74 seasons of Formula 1 racing, exploring how starting position, constructor, and era relate to race-day outcomes. Built with Python/pandas for data preparation and analysis, visualized in Tableau.

Research question: How has competitive balance in F1 changed over time, and what factors — grid position and constructor — are associated with race-day performance?

Dataset

Kaggle's Formula 1 World Championship dataset (1950–2024): 14 relational CSVs. This project uses seven — "races", "results", "drivers", "constructors", "circuits", "qualifying", "status" — merged into a single analytical table of ~26,800 race results.

Approach

- Load & inspect all tables; validate that foreign keys ("raceId", "driverId", "constructorId", "circuitId") line up across tables before joining anything.
- Build a master table by left-merging results with race, driver, constructor, and status details.
- Clean the position field into a numeric "finish_position", treating non-finishes carefully — cross-referencing the status table (engine failure, accident, disqualification, etc.) instead of collapsing everything into one generic "DNF."
- Derive "grid_to_finish = grid position − finish position", the core variable for measuring race-day position changes.
- Aggregate by constructor, by year, and by grid slot to build the tables behind each chart.

Dashboard

Built in Tableau Public, five charts:
[Live Dashboard](https://public.tableau.com/app/profile/bhuvaneshwari.b6518/viz/F1CompetitiveBalanceRace-DayPerformance/OverallDashboard?publish=yes)

1. Grid Position vs. Finish Position — scatter, shows the relationship between starting and finishing spot
2. Average Finish Position Over Time — season-by-season trend
3. Competitive Balance — leading constructor's share of points by year
4. Distribution of Position Changes — how many places drivers typically gain or lose per race
5. DNF / Non-Finish Rate by Year — reliability trend across F1 history

Key Findings

(Fill in with your actual numbers/observations, e.g.:)

- Starting position has a strong influence on finishing position, with the relationship weakening (more variance) further back on the grid.
- DNF rates have declined sharply from the earlier decades to under 20% in recent years — a clear reliability-engineering trend.
- Average finish position has drifted upward since the 1990s, largely tracking grid growth (more entrants) rather than a decline in competitiveness.
- [Add your competitive-balance takeaway once you're confident in that chart's read]

Limitations

- Constructor averages can be sensitive to sample size, particularly for teams with relatively few race entries.
- Season length varies across F1 history, so raw season-to-season point totals are not directly comparable without adjustment.
- A Top Constructors by Average Finish visualization was excluded because low-sample teams could skew the ranking.

Tools

Python (pandas, numpy, matplotlib, seaborn) · Jupyter Notebook · Tableau Public
