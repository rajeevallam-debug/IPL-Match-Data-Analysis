# IPL Match Data Analysis

An exploratory analysis of Indian Premier League (IPL) match results using Python and pandas. The notebook examines season-wise match counts, team and player records, toss decisions, venue results, match margins, D/L method usage, and finals.

## Project overview

This project uses a match-level IPL dataset to explore historical results and answer practical questions about the tournament. It includes basic data inspection and cleaning, followed by summary analyses using pandas.

The notebook reports 1,095 matches across 20 columns, spanning seasons from 2007/08 through 2024. Its results reflect the supplied dataset and the notebook's current cleaning and counting logic.

## Questions explored

- How many matches were recorded in each season?
- Which teams have the most recorded wins?
- How often did the toss-winning team also win the match?
- Which players received the most Player of the Match awards?
- Are teams more likely to choose batting or fielding after winning the toss?
- Which teams have the most wins at selected venues?
- What are the largest and smallest winning margins by runs or wickets?
- How many matches used the D/L method?
- Which teams have won the most finals in the dataset?

## Dataset

The notebook loads a local file named `matches.csv`. The file is not embedded in the notebook, so place the dataset in the same directory before running the analysis.

The dataset contains 1,095 rows and 20 columns, including:

- Season, date, city, match type, and venue
- Competing teams, toss winner, and toss decision
- Match winner, result type, and result margin
- Target runs and overs, Super Over indicator, and method
- Player of the Match and umpire fields

The notebook does not identify a dataset source or license. Add those details here if you redistribute the CSV.

## Tools and libraries

- Python
- Jupyter Notebook
- NumPy
- pandas

## Analysis and reported findings

The notebook reports these results from its current code and dataset:

- **Season counts:** The largest season totals shown are 76 matches in 2013, 74 in 2012, 2022, and 2023, and 73 in 2011.
- **Team wins:** Mumbai Indians (144), Chennai Super Kings (138), and Kolkata Knight Riders (131) have the highest counts in the raw winner column.
- **Toss and match result:** 554 rows have the toss winner matching the listed winner; the notebook reports this as 51% of all 1,095 rows.
- **Toss decisions:** Fielding was selected 704 times and batting 391 times.
- **Player awards:** AB de Villiers leads the displayed top ten with 25 Player of the Match awards, followed by CH Gayle with 22.
- **Selected venues:** Royal Challengers Bangalore has the most listed wins at M Chinnaswamy Stadium (29); Mumbai Indians leads at Wankhede Stadium (42).
- **Winning margins:** The largest run-margin win shown is Mumbai Indians by 146 runs. The largest wicket-margin win is by 10 wickets; the smallest displayed margins are 1 run and 1 wicket.
- **D/L method:** 21 rows have a non-null `method` value.
- **Finals:** Chennai Super Kings and Mumbai Indians lead the displayed final-win counts with five each.

These are descriptive counts, not adjusted comparisons. Team names appear in multiple historical forms in the dataset, and the notebook counts those forms separately. The toss comparison also uses all rows as its percentage denominator, including matches without a result.

## Data preparation

The notebook:

1. Loads `matches.csv` into a pandas DataFrame.
2. Inspects its dimensions, data types, sample rows, and missing values.
3. Fills missing city values with `"Unkwown"`, missing Player of the Match values with `"No Award"`, and missing winners with `"No Result"`.
4. Drops the `umpire1` and `umpire2` columns.
5. Runs grouped counts and filters to answer the questions above.

Other missing values, including `result_margin`, `target_runs`, `target_overs`, and `method`, remain in the DataFrame.

## Run the notebook

1. Clone or download this repository.
2. Place `matches.csv` beside `IPL_Data_Analysis.ipynb`.
3. Open the notebook in Jupyter Notebook, JupyterLab, or Google Colab.
4. Run the cells from top to bottom.

Install the required libraries if needed:

```bash
pip install numpy pandas jupyter
