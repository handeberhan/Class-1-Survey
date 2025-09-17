
# Class 1 Survey Data Analysis

## Project Description
This project analyzes a Class 1 survey dataset to practice R data skills and reproducible workflows. 
Using a single R script (analysis_code.R), this project imports the raw CSV, performs light cleaning 
(trimming text, standardizing common variable names like age and sex), and produces quick diagnostic summaries 
(dimensions, missingness, frequency tables). 
It then generates visualizations such as an age histogram, a sex distribution bar chart, and bar charts for several other categorical 
variables. It saves these visualizations to a plots/ folder. 

## Files Included
- `class1_survey.csv`: Cleaned version of the Class 1 survey dataset
- `analysis_code.R`: R script used to summarize and visualize the data
- `README.md`: This file

## What the Code Does
analysis_code.R does the following: 

Setup: 
1) Loads readr, dplyr, ggplot2, stringr, tidyr quietly.
2) Creates a plots/ folder if it doesn’t exist.

Data import: 
3) Expects class1_survey.csv in the working directory.
4) If the file isn’t found, it stops with a clear error message.

Light cleaning & standardization: 
5) Trims whitespace in all character columns.
6) Tries to standardize common names:
sex_at_birth, Sex, or (if sex absent) gender → sex
Age or AGE → age
7) Coerces age to numeric (safely, suppressing warnings).

Diagnostics printed to console: 
- Dataset dimensions (nrow, ncol).
- Missingness by column (count of NAs).
- Age summary (if age exists).
- Sex distribution (if sex exists).

Categorical profiling: 
8) Detects “categorical” columns as character/factor or numeric with ≤10 unique values.
9) Prints frequency tables for up to the first 6 detected categorical variables.

Visualization (saved to plots/): 
- plots/age_hist.png: histogram of age (if present).
- plots/sex_bar.png: bar chart of sex (if present).
- Up to 3 more bar charts for other categorical variables: plots/<col>_bar.png.

Outputs & side effects: 
10) Produces console summaries and PNG plots in plots/.
11) Does not overwrite or export a cleaned CSV.
12) Uses safe defaults (e.g., ggsave(width=6, height=4, dpi=150)).

## Description of dataset 
The Class 1 survey dataset is a convenience sample of students in a single course section. 
Each row is one student; columns are self-reported demographics and a small set of survey items. 

The dataset features this information: 
Who: Enrolled students in the ADA class.
When/where: Collected during Week 1 of the term .
How: Online questionnaire (e.g., Google Form/Qualtrics); no identifiers beyond general demographics.

## How to Run the Code
1) Run in RStudio
2) Open the folder in RStudio
3) Open analysis_code.R.
4) Set working directory to the script’s location
5) Click Source and run the code 

## Author
- Name: Hieran Andeberhan
- Course: ADA 
- Date: 06/2025

