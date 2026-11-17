# Strategy ETFs: covered call funds vs the market

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/YOUR-GITHUB-USER/YOUR-REPO/blob/main/strategy_etfs/strategy_etfs.ipynb)

Companion notebook to the Medium post **"Strategy ETFs: Why Covered Call Funds Are Winning Right Now, and When They
Won't"**, part 2 of the series that started with `theme_etfs`.

It compares seven covered call ETFs (JEPI, JEPQ, KNG, DIVO, GPIX, SPYI, OMAH) and produces:

1. **Theory charts (illustrative):** a call option's payoff, the implied volatility surface in a calm and a stressed
   market, and a covered call's payoff.
2. **Comparison table:** each fund's approach, options mechanism, option type, yield, expense ratio and launch date.
3. **Strategy map:** income (trailing yield) against the upside each fund actually kept (1-year up-capture vs the
   S&P 500), with expense ratio as bubble size and option type as the marker shape.
4. **Performance grid:** each fund vs SPY, DIA and QQQ as growth of $10,000, long term (left) and short term (right),
   with the VIX underneath, plus a total-return table for 1M to 5Y.

> **Not investment advice.** An educational exploration only. Data comes from Yahoo Finance through the
> unofficial `yfinance` library and may be incomplete, delayed or wrong.

## Run it

- **Colab:** click the badge above, then *Runtime → Run all*.
- **Locally:** `pip install -r requirements.txt`, then open `strategy_etfs.ipynb` in Jupyter and run all cells.

Data is cached in `data/` (set `REFRESH = True` to download again). Charts are saved to `charts/` as HTML and PNG,
tables as CSV.

## Change it

Everything is in the **Configuration** cell:

| Setting | What it does |
|---|---|
| `FUNDS` | The funds, in display order, with your one-line description of each and its option type |
| `REFERENCE` | Independent figures (expense ratio, distribution rate) used to fact-check Yahoo |
| `BENCHMARKS`, `VOL_INDEX` | What the funds are compared with, and the volatility index shown underneath |
| `LONG_PERIOD`, `SHORT_PERIOD` | Left column: `YTD`, `1Y`, `3Y`, `5Y`; right column: `1M`, `3M`, `6M` |
| `CAPTURE_PERIOD` | Window for measuring up-capture on the strategy map |
| `THEORY` | Inputs for the illustrative option charts (strike, days, volatility levels) |

Colors and fonts live in the **Style** cell, in the same pastel style as `theme_etfs` with different hues.

## Notes

- Funds younger than a chosen window show an empty panel labeled with their launch date.
- "Yield" is Yahoo's trailing 12-month yield. Funds often quote a distribution rate instead; the check table shows
  both where available.
- Returns are total returns (distributions reinvested), before taxes. Option income from these funds is taxed in
  very different ways; see the post.
