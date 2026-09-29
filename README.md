# Paper Leak Analysis

## Purpose

Analyze recorded examination paper-leak incidents in India from 2004–2026 using a structured data-analysis workflow.

## Project stages

1. Data Loading & Reading
2. Data Extraction, Validation & Cleaning
3. Data Aggregation, Representation & Analysis
4. Data Visualization, Results & Interpretation

## Required workflow

- Load and understand the dataset before making changes.
- Extract the information required for the project.
- Validate the dataset and clean identified data-quality issues.
- Aggregate and analyze the cleaned data.
- Visualize the main findings and interpret the results.

**Important:** The project describes recorded incidents in the dataset, not every paper-leak incident in India. Missing values are not automatically treated as zero, and the 2026 data covers only a partial year.

## Repository structure

- `01_Data_Loading_and_Reading/` — data loading, reading, category exploration and initial filtering
- `02_Data_Extraction_Validation_and_Cleaning/` — extraction, validation and cleaning
- `03_Data_Aggregation_Representation_and_Analysis/` — aggregation, representation and analysis
- `04_Data_Visualization_Results_and_Interpretation/` — visualization and interpretation
- `data/` — raw and cleaned project datasets
- `outputs/figures/` — exported visualization figures

## Dataset

The project uses the India Paper Leaks (2004–2026) dataset. The project dataset contains 110 recorded incidents and 18 fields.

The `data/` folder contains:

- `paper_leaks.csv` — raw project dataset
- `paper_leaks_cleaned.csv` — cleaned dataset used by later stages

**Important:** The raw dataset is preserved separately. The cleaned dataset is produced through the validation and cleaning process in Stage 2.

## Tools

Python, Pandas, NumPy and Matplotlib.
