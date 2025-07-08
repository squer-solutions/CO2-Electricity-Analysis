# CO2 and Electricity Access Analysis

## Tasks

1. In the `datasets` directory, you see several CSV files containing data points from https://data.worldbank.org and https://ourworldindata.org/. Your first task is to load those files into a common `Dataframe`. Study the data in terms of usability and quality. The `Dataframe` should only contain the intersection of countries in both datasets.

2. A customer wants an interactive Plot. Create two plots. Both plots should use the same color per country and should only contain countries that exist in both datasets. 

3. The customer wants to know if there is a connection between `Access to Electricity` and `CO2 Emissions`. He assumes that the easier electricity is accessible, the more likely electric cars, electrical furnaces, and heat pumps will be used. Can you provide an analysis?

> [!IMPORTANT]
> You can use whatever you want: Python, TypeScript, Julia, Pandas, Polars, Mojo, or even R and Excel. 
> Also, AI-assisted IDEs are welcome.
>
> Please feel free to generate all the code you want! Please explain it, however. **This challenge is not about your coding skills but your analytical thinking for data!** 

## Technical Provisioning

It is not required to use Python! However, if you want to make use of PDM

```bash
curl -sSL https://pdm-project.org/install-pdm.py | python3 -
pdm install
```

You will find the interpreter in `.venv/bin/python`