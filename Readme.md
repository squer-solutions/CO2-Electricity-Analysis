# CO2 and Electricity Access Analysis

## Tasks

1. In the `datasets` directory, you see several CSV files containing data points from https://data.worldbank.org and https://ourworldindata.org/. Your first task is to load those files into a common `Dataframe`. Study the data in terms of usability and quality. The `Dataframe` should only contain the intersection of countries in both datasets.

2. A customer wants an interactive Plot. Create two plots. Both plots should use the same color per country and should only contain countries that exist in both datasets. 

3. The customer wants to know if there is a connection between `Access to Electricity` and `CO2 Emissions`. He assumes that the easierlectricity, the more likely the usage of electric cars, electrical furnaces, and heat pumps will the access to e be. Can you provide an analysis?


## Instructions

You are free to use whatever you want. Python, TypeScript, Julia, Pandas, Polars, or Mojo. Or even R, if you like. Also, AI-assisted IDEs are free to go. 

If you generate your code, please explain it! Think critically. Search engines and manuals are free to use. 

## Technical Provisioning

It is not required to use Python! However, if you want to make use of PDM

```bash
curl -sSL https://pdm-project.org/install-pdm.py | python3 -
pdm install
```

You will find the interpreter in `.venv/bin/python`