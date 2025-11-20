🎲 Lottery Winning Number Analysis

A multi-game exploratory analysis of Powerball, Mega Millions, and Pick 10 draws

Overview

This project analyzes historical winning numbers from three major lottery games—Powerball, Mega Millions, and Pick 10—to explore number distributions, density patterns, and game-specific characteristics. The goal was not to “predict” lottery numbers but to visually and statistically examine patterns using Python and common EDA techniques.

Data Sources

Three datasets were used, each containing draw dates and winning numbers:

Powerball (2010–2024)

Mega Millions (2002–2024)

Pick 10 (1987–2024)

Each dataset includes a Winning Numbers column, which was split into separate columns through preprocessing to allow analysis of individual number positions.

Methods
1. Loading and Preparing the Data

All game CSVs were read into pandas, and draw dates were converted to datetime format. Winning numbers were split into Number_1, Number_2, … based on the maximum count of numbers per draw. A new column labeled Game was added for later grouping.

2. Combining Games

All three games were concatenated into a single dataset. To analyze the entire pool of drawn numbers, columns Number_1 through Number_6 were reshaped into a “long” format using pd.melt().

3. Kernel Density Estimation (KDE)

All numbers across all games were extracted and passed through Gaussian KDE to estimate the density of numbers drawn most frequently.

4. Visualizations

Several visualizations were created:

  • Density Plot of All Winning Numbers

Using KDE, the distribution of all numbers was visualized to observe whether some numbers occur more often.

  • Small Multiples: Histograms by Game

A subplot grid (3 rows × 1 column) was generated, where each plot showed the distribution of Number_1 for each game (Powerball, Mega Millions, Pick 10).

These plots allow comparison of number patterns between games with different rules and ranges.

Key Findings

  -  Drawn numbers across all games appear broadly uniform, as expected from random draws.

  -  KDE analysis showed minor clustering in some ranges, though these are not predictive.

  -  Each game has unique structural differences (different number counts and ranges), which become clear in the small-multiple histograms.

  -  Pick 10 draws show different patterns due to having 10 numbers per draw and a broader number range.

Requirements

  -  Python 3.x

  -  pandas

  -  numpy

  -  matplotlib

  -  scipy (for gaussian_kde)

Install dependencies:
pip install pandas numpy matplotlib scipy

How to Run

  - Open the notebook or HTML export (Lottery_Number_Analysis.html).

  -  Ensure your lottery CSV files are placed in the correct directory.

  -  Run all cells.

  -  View density plots, histograms, and reshaped datasets.

Future Enhancements

  -  Compare hot/cold number trends over time

  -  Build an interactive dashboard in Power BI or Tableau

  -  Add support for additional lottery games

  -  Explore temporal clustering of draw sequences

Files Included

  -  Lottery_Number_Analysis.html – exported notebook with full code and visuals

  -  Raw datasets for Powerball, Mega Millions, and Pick 10

  -  Project README
