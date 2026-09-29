# Stage 2 — Data Extraction, Validation & Cleaning

## Purpose

Extract the information required for the project analysis, identify common data-quality issues, and apply only the necessary cleaning steps to prepare the dataset for later stages.

## Required checks

- Extract selected fields such as incident location, exam name and other required information.
- Identify high-confidence incidents and cases involving central conducting bodies.
- Extract incidents with recorded arrests and All India level incidents.
- Check for missing values and calculate missing-value percentages.
- Check for duplicate records and duplicate Incident IDs.
- Validate Incident ID format and date values.
- Check for blank text values and unnecessary leading or trailing spaces.
- Apply the required cleaning steps based on the validation results.
- Preserve missing values where the source does not report information instead of automatically replacing them with zero.

**Important:** The original dataset is kept separate from the cleaned dataset. Cleaning is performed only where a data-quality issue is identified.

## Output

The stage produces the validated and cleaned dataset used by the aggregation, analysis and visualization stages of the project.
