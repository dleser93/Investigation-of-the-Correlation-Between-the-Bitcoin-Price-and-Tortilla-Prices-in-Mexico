# Investigation of the Correlation Between the Bitcoin Price and Tortilla Prices in Mexico

![image.png](https://zenodo.org/badge/DOI/10.5281/zenodo.11080415.svg)

Tyler Vigen shows on his homepage (http://www.tylervigen.com) many examples of spurious correlations, which remind us that correlation does not imply causation. Inspired by his work, this project shows a further bizarre correlation between the Bitcoin price and the tortilla prices in Mexico.

## Project Overview:
The input for this project are three datasets. The first dataset contains the tortilla prices in Mexican Peso (MXN) for big retail stores and mom-and-pop stores for various states and cities in Mexico. The second dataset contains the daily closing prices of Bitcoin in US dollar (start date = ”2007-01-10”; end date = ”2024-02-28”). The third dataset contains the daily currency exchange rates, in order to convert the Mexican Peso (MXN) in the first dataset into US dollar (start date = ”2007-01-10”; end date = ”2024-02-28”). At the end, the output of this project are the Spearman correlation coefficients between the daily closing prices of Bitcoin and the mean tortilla prices for each state (aggregated over the prices per cities in the corresponding state) as well as separated for big retail stores and mom-and-pop stores.

## Folder Structure:
* data
  * **input datasets:** tortilla_prices.csv, yahoo_bitcoin_data_2024-03-19.csv and yahoo_ex_rates_data_2024-03-19.csv
  * **metadata for input datasets:** tortilla_prices-metadata.json, yahoo_bitcoin_data_2024-03-19-metadata.json and yahoo_ex_rates_data_2024-03-19-metadata.json
* results
  * **output dataset:** results_spearman_corr.csv
  * **metadata for output dataset:** results_spearman_corr-metadata.json

## Used Software and Libraries:
* Jupyther Notebook
* Python 3.7
* pandas 2.1.4
* numpy 1.26.3
* matplotlib 3.8.0
* yfinance 0.2.38 (was used to download the datasets yahoo_bitcoin_data_2024-03-19.csv and yahoo_ex_rates_data_2024-03-19.csv, which is not necessary to reproduce the results)

## Metadata:
All metadata files follow the CSVW Namespace Vocabulary Terms for metadata from W3C and contain common metadata such as title, description and datatype. The vocabulary and term explanation of this standard is available at https://www.w3.org/ns/csvw.

## Input Datasets:
* **tortilla_prices.csv:** This dataset contains the tortilla prices in Mexican Peso per kilogram (start date = "2007-01-10"; end date = "2024-03-01") for big retail stores and mom-and-pop stores for various states and cities in Mexico. The original source of this dataset is https://www.kaggle.com/datasets/richave/tortilla-prices-in-mexico (creator: Rick Chavelas; license: CC0: Public Domain) and was downloaded from the original source on the 19th of March, 2024.
* **yahoo_bitcoin_data_2024-03-19.csv:** This dataset contains the daily Bitcoin prices in US dollar (USD) and was downloaded from https://finance.yahoo.com/ on the 19th of March, 2024 (start date = ”2007-01-10”; end date = ”2024-02-28”).
* **yahoo_ex_rates_data_2024-03-19.csv:** This dataset contains the daily currency exchange rates to convert Mexican Peso (MXN) into US dollar (USD) and was downloaded from https://finance.yahoo.com/ on the 19th of March, 2024 (start date = ”2007-01-10”; end date = ”2024-02-28”).

## Output Dataset:
* **results_spearman_corr.csv:** This dataset contains the results of this project, which are the Spearman correlation coefficients between the daily closing prices of Bitcoin (start date = ”2014-09-17”; end date = ”2024-02-27”) and the mean tortilla prices (start date = ”2014-09-17”; end date = ”2024-02-27”) for various states of Mexico (aggregated over the prices per cities in the corresponding state) as well as separated for big retail stores and mom-and-pop stores.

## Code Explanation:
The Jupyter Notebook file Spearman_Corr_Bitcoin_Tortilla.ipynb contains the whole code of this project and is structured in the following sections:

**1. Read Data:** Reads the input datasets tortilla_prices.csv, yahoo_bitcoin_data_2024-03-19.csv and yahoo_ex_rates_data_2024-03-19.csv from the folder "data".

**2. Transform Year, Month and Day to datetime Object:** Uses the columns "Year", "Month" and "Day" of the dataset tortilla_prices.csv to create a datetime object for each observation.

**3. Cut Time Series to Same Length:** This section looks for the earliest and the lastes dates in all input datasets and creats one common timeline from the earliest common date (2014-09-17) until the lastest common date (2024-02-27).

**4. Remove Missing Values:** Removes the missing values of the dataset tortilla_prices.csv.

**5. Transform Mexican Pesos to US Dollar:** This sections converts the tortilla prices per kilogram in Mexican Peso (MXN) into US dollar (USD).

**6. Aggregate Price for Each State:** For each day, this section aggregates the tortilla prices per kilogram of all cities in a state to one tortilla price per kilogram for the correspondig state and day.

**7. Merge Data:** Merges the necessary features (date, closing Bitcoin prices, aggregated tortilla prices per kilogram, state and store type) into one dataframe.

**8. Plot Data:** This section plots the closing Bitcoin prices and aggregated tortilla prices per kilogram in big retail stores and mom-and-pop stores over time with line charts.

**9. Calculate Spearman Correlations:** Calculates the Spearman correlation coefficients between the daily closing prices of Bitcoin and the mean tortilla prices for each state (aggregated over the prices per cities in the corresponding state) for big retail stores and mom-and-pop stores.

**10. Plot and Save Results:** This section plots the calculated Spearman correlation coefficients with bar charts separated for big retail stores and mom-and-pop stores.

**11. Interpretation of the Results:** Interpretation of the results based on Cohen (1988), who defined guidelines to interpret Pearson and the Spearman correlation coefficients.


