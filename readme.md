# Class 1 Survey Data Analysis

## Project Description
This repository includes the Class 1 survey dataset and R markdown code used to analyze it. The project is part of an exercise to practice working with real-world data in R markdown.

## Files Included
- `Class 1 Survey Fall 2025 2.csv`: Cleaned version of the Class 1 survey dataset
- `classsurvey.Rmd`: R script used to summarize and visualize the data
- `readme.md`: This file

## What the Code Does
# Class Survey Analysis — Step by Step

1. **Setup**
   - Load packages: `tidyverse`, `readr`.

2. **Import data**
   - Read the CSV into `C1survey` with `read_csv(...)`.

3. **Basic dimensions**
   - Report number of rows with `nrow(C1survey)`.
   - Report number of columns with `ncol(C1survey)`.

4. **Rename variables**
   - Define a vector of new names (`new_names`) that matches the column count.
   - Assign with `names(C1survey) <- new_names` and display with `names(C1survey)`.

5. **Inspect data types**
   - Show each column’s class using `sapply(C1survey, class)`.
   - Summarize class frequencies with `table(sapply(C1survey, class))`.

6. **Explore & clean birthdays**
   - Tabulate raw `bday` and `bmonth` (including NAs).
   - Clean `bday`:
     - Coerce numeric where possible or extract numbers from text (e.g., `“June 2nd”` → `2`).
     - Keep values 1–31; otherwise set to `NA`.
   - Clean `bmonth`:
     - Accept numeric 1–12 or map month text/abbreviations to numbers (fixes typos like `“septemeber”`).
   - Compute medians of cleaned `bday` and `bmonth` with `median(..., na.rm = TRUE)`.

7. **Derive birth season**
   - Create `bseason` (Winter: 12–2, Spring: 3–5, Summer: 6–8, Fall: 9–11) as an ordered factor.
   - Build a month × season table with `table(bmonth, bseason, useNA = "ifany")`.
   - Get classmates per season via `colSums(...)`.

8. **Summarize favorite month**
   - Count and sort favorite months (`fav_month`) using `count(fav_month, sort = TRUE)` after removing blanks/NAs.


## How to Run the Code
1. Download or clone this repository to your computer
2. Open `analysis_code.Rmd` in RStudio
3. Make sure your working directory is set to the folder where the files are saved
4. Run the script

## Author
- Name: Michael Tebeje  
- Course: Advanced Data Analysis
- Date: September 2025
