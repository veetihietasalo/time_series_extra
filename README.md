# time_series_extra

Rendered notebook: https://veetihietasalo.github.io/time_series_extra/ (the saved outputs, not re-run)

One Jupyter notebook, `aikasarjat_extra.ipynb`, with short examples in Finnish (aikasarjat = time series) on working with time series in pandas. Made in Google Colab in March 2024.

It's a small teaching notebook, not a research project. It shows what a date index gives you in pandas, and what volatility looks like on a series you can see.

## What's inside

16 cells:

- Loads seaborn's `dowjones` dataset (649 monthly prices from December 1914) and shows that the date column is `datetime64`.
- Builds a daily date index with `pd.date_range` for 400 random values from 2020-01-01 and plots a date slice (1 to 20 December 2020).
- Volatility: three random 60-day series around 100 with standard deviations 1, 10 and 50, plotted side by side. Then a 10-day rolling standard deviation scaled by √252, one plot per series.

The rolling figure is taken from the values, not from returns, so it's an illustration of the idea and not a volatility estimate.

## Run

Open it in [Colab](https://colab.research.google.com/github/veetihietasalo/time_series_extra/blob/master/aikasarjat_extra.ipynb), or locally:

```
pip install pandas numpy matplotlib seaborn jupyter
jupyter notebook aikasarjat_extra.ipynb
```

`sns.load_dataset` downloads the data, so it needs internet. The random values have no seed, so the plots differ from the saved outputs. I ran the code cells as a script with current pandas and seaborn: the data loads (649 rows), the index builds (400 rows) and the rolling series has 51 values per plot.

## How it was built

The notebook is mine (Colab commit, 2024-03-06). A coding agent wrote this README and rendered the notebook to the `gh-pages` branch in October 2026, with `jupyter nbconvert --to html` on the saved outputs and the Colab-only scripts left out.

## What I learned

- A `datetime64` column or index lets pandas slice by date strings, `df['hinta']['2020-12-1':'2020-12-20']`, and plot the slice directly.
- Volatility is spread around a level. The same average of 100 is easy to predict at a standard deviation of 1 and hard at 50.
- Annualising a daily figure is × √252, the trading days in a year.
- Rolling volatility belongs on returns, not on prices or raw values. This notebook doesn't do that yet.

## Status

The repo started in 2018 as a first Git test (`hello_world.txt`). The notebook was added on 2024-03-06, no updates since. No license file in this repo yet.
