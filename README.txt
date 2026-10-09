COMP20008 Assignment 2 - W14G04

Dathen Seneviratne 1564286
Richard Chen 1760214
Yohance Espina  1615451
=================================

## Research question

Can multi-listing ("professional") hosts be distinguished from single-listing
hosts, and what operating differences are visible in Melbourne Airbnb data?

## Contents

- `code.ipynb`: reproducible notebook containing preprocessing, correlation
  analysis, supervised learning, feature selection, uncertainty analysis, and
  figure generation.
- `listings.csv`: Melbourne listing-level data used by the notebook.
- `requirements.txt`: Python package dependencies.

## Data source

The input data is the Melbourne listings dataset from Inside Airbnb. The
dataset contains 25,728 listing-level observations. See the report references
for the full APA citation.

## Setup

1. Use a Python environment with Jupyter available.
2. From this directory, install the dependencies:

   ```bash
   python3 -m pip install -r requirements.txt
   ```

3. Keep `listings.csv` in the same directory as `code.ipynb`.

## How to reproduce the analysis

1. Start Jupyter Notebook or JupyterLab from this directory.
2. Run all notebook cells in 'code.ipynb' sequentially.

The notebook reads `listings.csv`, prints the intermediate and final result
tables used in the report, and regenerates the PNG figures in `figures/`.

## Reproducibility notes

- The train/test split, cross-validation, mutual-information estimators, and
  bootstrap analysis use `random_state=42` where applicable.
- The correlation analysis uses four variables: `is_multi_listing`,
  `days_since_last_review`, `reviews_per_month`, and `review_scores_rating`.
- Listings without a recorded review are not assigned an artificial review
  date. The correlation analysis therefore uses the 21,251 complete reviewed
  listings; 4,477 listings with no review record are excluded from that
  analysis only.

## Expected outputs

Running the notebook produces:
- preprocessing summaries, including missing-value impacts;
- the correlation bin summary and six-row correlation-results table;
- KNN and Decision Tree tuning and test-set evaluation results;
- filter and embedded feature-selection rankings;
- bootstrap macro-F1 confidence intervals; and
