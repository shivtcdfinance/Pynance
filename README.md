📈 Technical Analysis Dashboard — Golden Cross, RSI & MACD (Python)

This project is a single-file Python analysis tool that builds a full technical analysis dashboard for any price time-series CSV (ETF, stock, index).

It computes and visualises:

50-day & 200-day Moving Averages

Golden Cross events

RSI (14)

MACD (12, 26, 9)

Large price discontinuities (possible stock splits / bonus issues / data breaks)

All results are displayed in one consolidated dashboard figure, avoiding fragmented plots and scroll-heavy outputs.

🔍 What the dashboard shows

The output consists of six vertically stacked panels:

Full history

Price + MA50 / MA200 with:

Golden Cross markers

≥50% single-day move flags (split/bonus detection)

RSI (14) with overbought / oversold levels

MACD with signal line and histogram

Recent window (user-defined)

Price + MA50 / MA200 for the last N years

RSI (14) for the same period

MACD for the same period

This structure allows long-term regime analysis and recent trend inspection in one view.

⚙️ How it works

Reads the CSV once and builds all indicators in a single DataFrame

Uses vectorised pandas operations (no loops)

Filters recent data using a configurable YEARS_BACK parameter

Plots everything into one Matplotlib figure for clarity

🛠️ Configuration (only section you need to edit)
FILE = "your_file.csv"
PRICE_COL = "Price"   # or "Close"
YEARS_BACK = 2        # recent window length


Drop any CSV with a Date column and a price column into the folder and rerun.

📊 Output tables

In addition to charts, the script prints:

Golden Cross event table (date, price, MA values)

Potential split/bonus event table (dates with ≥50% daily moves)

🎯 Use cases

Technical screening of ETFs or stocks

Identifying long-term trend regime changes

Detecting data breaks, splits, or structural adjustments

Exploratory market analysis in Jupyter notebooks

Educational or research-focused technical analysis

📦 Requirements

Python 3.x

pandas

numpy

matplotlib

Jupyter Notebook (recommended)

🧠 Notes

Indicators are computed on the full dataset to avoid warm-up distortion.

Recent-period plots are filtered after indicator calculation.

The split/bonus flag is heuristic and meant as a signal, not confirmation.
