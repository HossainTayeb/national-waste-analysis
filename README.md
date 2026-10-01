# National Waste Report 2022 — Data Analysis

Data cleaning, wrangling, and exploratory analysis of Australia's National Waste Report 2022 dataset, examining waste generation, recovery, and fate across Australian states from 2006-2021.

## Overview

This project analyses waste management data covering Australian states, identifying patterns in waste categories, recycling and disposal fates, and state-level trends. The work covers a full data-cleaning pipeline (handling inconsistent labels, missing values, malformed dates, and data entry errors) followed by targeted exploratory analysis and visualisation.

## Features

- Data quality auditing: systematic detection of missing values, duplicate identifiers, inconsistent categorical labels, and numeric anomalies (including a corrupted value recovered from embedded text and a spreadsheet autofill error in year data).
- Text parsing: extraction of structured fields (environmental impact score, qualitative feedback, stated tonnage) from free-text description fields using regular expressions.
- Exploratory analysis: waste-source composition by category, state-level summary statistics, yearly trend analysis, and correlation testing.
- Data visualisation: stacked bar charts, boxplots, and trend lines built with ggplot2.
- External validation: cross-checking internal trend findings against published Australian Bureau of Statistics and DCCEEW figures.

## Tech Stack

- R - analysis language
- tidyverse (dplyr, ggplot2, stringr, tidyr) - data wrangling and visualisation
- R Markdown - literate programming / reproducible report generation

## Project Structure

national-waste-analysis/
  waste_report_analysis.Rmd    - Main analysis notebook
  waste_report_analysis.html   - Knitted report output
  data/                        - Source CSV files
    Wastes.csv
    Year_State_ID.csv
  docs/                        - Data dictionary and notes

## Installation

Clone the repository:

    git clone https://github.com/HossainTayeb/national-waste-analysis.git
    cd national-waste-analysis

Install required R packages:

    install.packages("tidyverse")

## Usage

Open waste_report_analysis.Rmd in RStudio and click Knit, or run:

    rmarkdown::render("waste_report_analysis.Rmd")

The pre-rendered report is also available directly: open waste_report_analysis.html in a browser.

## Data

Source: National Waste Report 2022 dataset (Wastes.csv, Year_State_ID.csv), covering waste generation, recovery, and fate across Australian states, 2006-2021. See docs/data_dictionary.md for column definitions.

## Key Findings

- Waste source composition varies strongly by material category - e.g. construction and demolition materials are ~96% construction/demolition-sourced, while glass is ~78% municipal solid waste.
- Recycling consistently receives higher environmental impact scores than disposal; waste category and disposal method (Fate) are meaningfully associated with impact scores, while total tonnage and state economic growth are not.
- Total construction and demolition waste tonnes rose sharply from 2013 onward, a trend that partially aligns with, but also partially diverges from, published national benchmarks - likely reflecting improvements in national waste-reporting methodology alongside genuine growth in construction activity.

## Future Improvements

- Parameterise the analysis to support additional years as new National Waste Report editions are released.
- Add automated data-quality tests (e.g. testthat) to formalise the checks currently performed manually.

## License

MIT - see LICENSE file

## Author

Tayeb - Master of Data Science, Monash University
