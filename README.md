# Prize-Winning Hackathon Solution — Sales Rhythms (All Cups)

This folder contains the complete GitHub-ready package for my **prize-winning solution** to the **All Cups "Sales Rhythms"** forecasting challenge.

## Best Public Result

- **Public wMAE:** 1.787
- **Public Score:** 0.359
- **Best submission file:** `submission_v7_t1.8.csv`
- **Reproducible notebook:** `submission_v7_t1.8.ipynb`

## Included Files

- `submission_v7_t1.8.ipynb` — final notebook with full pipeline
- `submission_v7_t1.8.csv` — best public submission
- `train.parquet` — training dataset
- `test.parquet` — test dataset
- `sample_submission.csv` — submission template
- `All Cups _ Задача - Ритмы продаж.pdf` — original task statement

## Method Summary

- LightGBM (`regression_l1` / MAE objective)
- Weighted training (`w=7` for `qty>0`, `w=1` for `qty=0`)
- 18 engineered features (calendar, price, promo, leftovers, lags, rolling stats)
- Iterative 14-day prediction with daily lag updates
- Post-processing with leftover clipping, thresholding (`1.8`), and rounding

## How to Use

1. Open `submission_v7_t1.8.ipynb`.
2. Ensure the notebook path points to this folder.
3. Run all cells to reproduce predictions.
4. Output will be saved as `submission_v7_t1.8.csv`.
