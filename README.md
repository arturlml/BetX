# BetX

Football corner-kick analysis in Python. The notebooks combine historical match data from Brasileirao Serie A, the Premier League and La Liga, compute per-team rolling statistics for corners, and flag fixtures in the upcoming round where corner patterns are consistent.

## How it works

1. **Historical data**: loads match history (2022/23 and 2023/24 seasons for La Liga and the Premier League, 2023 for Serie A) from public Excel datasets.
2. **Team features**: for each team, computes a 5-match rolling mean and coefficient of variation (CV) of corners won, conceded and total, split by home and away.
3. **Upcoming fixtures**: loads the next-round schedules from the `.xlsx` files in this repo (`Brasileirao_SerieA.xlsx`, `Premier_Games.xlsx`, `LaLiga_Games.xlsx`).
4. **Selection**: keeps fixtures where both teams have CV <= 0.5 for corners won, estimates expected corners per side as the minimum of one team's attack average and the opponent's defensive average, and exports the shortlist to Excel.

## Notebooks

| Notebook | Purpose |
|---|---|
| `BetX_Mundo.ipynb` | Prompts for the round number of each league and builds the shortlist |
| `BetX_Mundo_next_round.ipynb` | Selects the next round automatically from the current date and includes corner odds columns |
| `BetX_Test2.ipynb` | Early experiment |

## Stack

Python, pandas, Jupyter

> Personal analytics project (2023). Not betting advice.
