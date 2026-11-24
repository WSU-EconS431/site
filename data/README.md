# Data snapshots

Course datasets are stored here as snapshots, so notebooks run the same way every
term and without a network connection. Each entry gives the source, the date the
snapshot was taken, and what was changed. Never edit a snapshot by hand; if a file
needs a fix, redo it from the source and update this page.

Snapshots taken **2026-11-21** unless noted.

## `mpd2020_full.csv`: Maddison Project Database 2020

- **What:** GDP per capita and population for 169 countries, from year 1 to 2018
  (annual from 1950 for most countries; sparse before that). Columns: `countrycode`,
  `country`, `year`, `gdppc` (GDP per capita, 2011 international dollars), `pop`
  (population, thousands).
- **Source:** Bolt, Jutta and Jan Luiten van Zanden (2020), "Maddison style estimates of
  the evolution of the world economy. A new 2020 update," Maddison Project Working Paper
  WP-15, Groningen Growth and Development Centre. License CC BY 4.0. Project page:
  <https://www.rug.nl/ggdc/historicaldevelopment/maddison/releases/maddison-project-database-2020>.
- **Copy used:** the `mpd2020.xlsx` file that the QuantEcon lecture series hosts at
  <https://github.com/QuantEcon/data-lectures/raw/main/lectures/mpd2020.xlsx>
  (downloaded 2026-11-21).
- **Changes:** sheet "Full data" saved as CSV; nothing else. Missing values are empty.
- **Known quirk:** the source has `gdppc = 0` for the United Arab Emirates in 1991 and 1992
  (population is positive). These look like placeholders for missing estimates. The snapshot keeps them
  as downloaded; course notebooks set them to missing and say so.

## `country_groups.csv`: a small region lookup (made for this course)

- **What:** 26 countries from the Maddison file, each assigned to one of eight world
  regions (`countrycode`, `region`). It exists so the merge exercises have a second table.
- **Source:** compiled by the instructor using region names like those in the Maddison
  Project's regional tables. It is **not** an official classification and covers only
  26 of the 169 countries on purpose.

## `us_macro_1959_2009.csv`: US quarterly macroeconomic data

- **What:** 203 quarters, 1959Q1 to 2009Q3: real GDP, consumption, investment, federal
  spending, disposable income (billions of chained 2005 dollars, seasonally adjusted
  annual rates), CPI, M1, the 3-month T-bill rate, the unemployment rate, population,
  and inflation and real interest rate series derived from them.
- **Source:** the `macrodata` dataset distributed with the `statsmodels` Python package
  (compiled by Skipper Seabold from the Federal Reserve Bank of St. Louis FRED database,
  except unemployment from the Bureau of Labor Statistics; accessed by its compiler
  2009-12-15). Read from the statsmodels installation on 2026-11-21.
- **Changes:** `year` and `quarter` stored as integers; nothing else.

## `nber_recessions.csv`: US recession dates

- **What:** the eight US recessions that start in 1960 or later and end by 2009 (month
  of the NBER business-cycle peak and trough, and the quarter containing each).
- **Source:** NBER Business Cycle Dating Committee, "US Business Cycle Expansions and
  Contractions," <https://www.nber.org/research/data/us-business-cycle-expansions-and-contractions>
  (checked 2026-11-21).
