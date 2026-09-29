# Dataset

## Purpose

Store the raw and cleaned CSV files used by the project stages.

## Required files

- `paper_leaks.csv` — original/raw project dataset used in Stage 1 and Stage 2.
- `paper_leaks_cleaned.csv` — cleaned dataset produced by Stage 2 and used by Stage 3 and Stage 4.

## Dataset information

The project uses the India Paper Leaks (2004–2026) dataset containing recorded paper-leak incidents and the fields required for extraction, validation, cleaning and analysis.

**Important:** Keep the original/raw dataset separate from the cleaned dataset. Missing values should not be automatically replaced with zero when they represent information that was not reported.

## Output

The raw dataset is preserved for reference, while the cleaned CSV provides the common input for the aggregation, analysis and visualization stages.
