# AI On-site Challenges

If you're not instructed otherwise, please start with 

1. [The data science challenge](./1_DataScience_Challenge.md) 

## Getting Started

### Option 1 — Local setup with uv

It is not required to use Python! However, if you want to, we recommend [uv](https://docs.astral.sh/uv/):

```bash
# Install uv (macOS/Linux) — see https://docs.astral.sh/uv/ for other options
curl -LsSf https://astral.sh/uv/install.sh | sh

# Windows (PowerShell)
# powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"

# Create the environment (auto-installs Python 3.13 + all dependencies)
uv sync
```

Then run your analysis:

```bash
# Option A — run a script directly
uv run python your_analysis.py

# Option B — Jupyter Lab (pulled in on the fly, no dependency change)
uv run --with jupyterlab jupyter lab
```

You will find the interpreter in `.venv/bin/python`.

### Option 2 — Google Colab (no local setup)

Prefer to work in the browser? Open [Google Colab](https://colab.research.google.com/) and, in a new notebook, clone the repository:

```python
!git clone https://github.com/squer-solutions/CO2-Electricity-Analysis.git
%cd CO2-Electricity-Analysis
```

Most libraries (pandas, plotly, scipy, statsmodels) are preinstalled in Colab; install the rest on demand, e.g.:

```python
!pip install polars
```

The datasets are now available under `datasets/`, ready to load.


> [!IMPORTANT]
> To us, it is important to see how you think, analyze, and fit certain tools together. There is no need to do
> something in one specific technology as long as you have a sufficient replacement. Overall, the most
> important part is to get the job done and ask the right questions. 

Have fun and good luck! 