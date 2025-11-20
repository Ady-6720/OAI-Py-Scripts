# Run Order

## Step 1: Run `DataCleaning.ipynb`

This notebook must always run first. It performs the full data preparation workflow:

* Loads `Main.csv`.
* Prints the initial dataset shape.
* Normalizes all column names by removing long prefixes, fixing typos, and applying title-case formatting.
* Standardizes all College values using a controlled mapping.
* Standardizes all Event values by adding numeric prefixes for stable sorting.
* Prints the final dataset shape to confirm it matches the initial shape.
* Exports the cleaned dataset as `main_clean.csv`.

No rows are removed in this process. If the initial and final shapes differ, the cleaning introduced an issue.

## Step 2: Run `NameStandardization.ipynb`

This notebook should be executed only after `main_clean.csv` has been generated. It depends on the cleaned dataset produced in Step 1 and applies any additional renaming, validation, or downstream transformations that rely on the standardized structure.
