# AvoCast — Forecasting U.S. Avocado Prices with Prophet

Project report for **DLBAIBEPAIPC01 — Project: AI Product Commercialisation**
IU Internationale Hochschule · Semester 2, May 2026
Author: Marvin Neumann · Matriculation No. IU14156706

## What this is

A small forecasting prototype that turns three years of weekly U.S. avocado-price data into a **12-week forward forecast** for one regional market (SanDiego, conventional), using **Facebook Prophet**. The forecast is then translated into four concrete actions a retailer could take next quarter.

The report covers business understanding, data EDA with statistical tests (ADF, ACF, price-volume correlation), the Prophet model build, an honest error / robustness / over-underfitting discussion, business translation, and a reflection on what worked, what did not, and how the prototype could grow.

## Repository layout

```
avocast/
├── README.md
├── requirements.txt
├── docs/
│   ├── report.md          ← report source (markdown)
│   ├── report.pdf         ← final submitted PDF (14 pages)
│   ├── title-page.html    ← title page used at build time
│   └── style.css          ← IU academic style (Times 12pt, justified, A4)
├── notebooks/
│   └── avocast.ipynb      ← the Prophet build: pandas + EDA + train + plots
├── assets/
│   ├── canvas-sketch.png  ← project canvas (Excalidraw)
│   ├── dashboard-sketch.png ← dashboard sketch (Excalidraw)
│   ├── trello-board.png   ← Trello planning board
│   ├── forecast.png       ← Prophet forecast vs. actual
│   └── components.png     ← Prophet components (trend, holidays, yearly)
├── decisions/             ← project decision log
└── notes/                 ← working notes
```

## Reproducing the forecast

```bash
python3 -m pip install -r requirements.txt

# Place the Kaggle dataset (https://www.kaggle.com/datasets/neuromusic/avocado-prices)
# as data/avocado.csv

jupyter notebook notebooks/avocast.ipynb
# Run all cells.
```

## Rebuilding the PDF

```bash
cd docs
pandoc report.md -o report.html \
  --standalone --embed-resources \
  --css=style.css --toc --toc-depth=2 \
  --include-before-body=title-page.html

# Convert HTML → PDF (Chrome headless)
"/Applications/Google Chrome.app/Contents/MacOS/Google Chrome" \
  --headless=new --disable-gpu --no-pdf-header-footer \
  --print-to-pdf=report.pdf "file://$(pwd)/report.html"
```

## Key results

- **MAPE on 34-week hold-out:** 19.57 %
- **MAE:** \$0.237 per avocado
- **Holiday effects learned:** Thanksgiving **+\$0.23**, Christmas/NY **+\$0.04**, Super Bowl **−\$0.12**, Cinco de Mayo **−\$0.11** (the negatives reflect retailer promo behaviour, not lack of demand)
- **Trend:** dipped to \$0.89 in Jan 2016, climbed steadily to \$1.41 by Mar 2018; 8 significant change points all clustered Nov 2015 to May 2016
- **Seasonality:** peak in October (\$1.33 monthly mean), trough in February (\$0.88)
- **Price-volume correlation:** Pearson r = **−0.75** (textbook law of demand + promo-driven price drops)

## Data source

Hass Avocado Board / `neuromusic` (2018). *Avocado Prices* [Dataset]. Kaggle.
<https://www.kaggle.com/datasets/neuromusic/avocado-prices>

The dataset itself is intentionally **not** committed to this repository.

## Tools

- [Facebook Prophet](https://facebook.github.io/prophet/) — additive time-series model
- pandas, matplotlib, statsmodels (for ADF + ACF)
- Excalidraw — hand-drawn sketches for canvas and dashboard
- Pandoc + Chrome headless — Markdown → PDF pipeline

## License

This project is submitted academic work. Code is provided for review; the report text remains the author's.
