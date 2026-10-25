# time_series_extra

One Jupyter notebook, `aikasarjat_extra.ipynb` (aikasarjat = time series), with short examples in Finnish on working with time series in pandas. Made in Google Colab in March 2024.

What's in it (16 cells):

- Loads seaborn's `dowjones` dataset (649 monthly prices from December 1914) and shows that the date column is `datetime64`.
- Builds a daily date index with `pd.date_range` for 400 random values from 2020-01-01 and plots a date slice (1 to 20 December 2020).
- Volatility: three random 60-day series around 100 with standard deviations 1, 10 and 50, plotted side by side, then a 10-day rolling standard deviation scaled by sqrt(252). The rolling figure is taken from the values, not from returns.

Stack: Python, pandas, NumPy, matplotlib, seaborn.

## Run

Open the notebook in Colab, or locally:

```
pip install pandas numpy matplotlib seaborn jupyter
jupyter notebook aikasarjat_extra.ipynb
```

`sns.load_dataset` downloads the data, so it needs internet. The random values have no seed, so the plots differ from the saved outputs.

Status: the repo started in 2018 as a first Git test (`hello_world.txt`). The notebook was added on 2024-03-06, no updates since.
