# Investigation of the Correlation Between the Bitcoin Price and Tortilla Prices in Mexico

![image.png](https://zenodo.org/badge/DOI/10.5281/zenodo.11080415.svg)

Tyler Vigen shows on his homepage (http://www.tylervigen.com) many examples of spurious correlations, which remind us that correlation does not imply causation. Inspired by his work, this project shows a further bizarre correlation between the Bitcoin price and the tortilla prices in Mexico.

The input for this project are three datasets. The first dataset contains the tortilla prices in Mexican Peso (MXN) for big retail stores and mom-and-pop stores for various states and cities in Mexico. The second dataset contains the daily closing prices of Bitcoin in US dollar (start date = ”2007-01-10”; end date = ”2024-02-28”). The third dataset contains the daily currency exchange rates, in order to convert the Mexican Peso (MXN) in the first dataset into US dollar (start date = ”2007-01-10”; end date = ”2024-02-28”). At the end, the output of this project are the Spearman correlation coefficients between the daily closing prices of Bitcoin and the mean tortilla prices for each state (aggregated over the prices per cities in the corresponding state) as well as separated for big retail stores and mom-and-pop stores.

## Folder Structure:
* data
 * input datasets: tortilla_prices.csv, yahoo_bitcoin_data_2024-03-19.csv and yahoo_ex_rates_data_2024-03-19.csv
 * metadata for all input datasets: tortilla_prices-metadata.json, yahoo_bitcoin_data_2024-03-19-metadata.json and yahoo_ex_rates_data_2024-03-19-metadata.json
* results
 * output dataset: results_spearman_corr.csv
 * metadata for output dataset: results_spearman_corr-metadata.json

## Used Software and Libraries:
* Python 3.7
* Jupyther Notebook
* pandas 2.1.4
* numpy 1.26.3
* matplotlib 3.8.0
* yfinance 0.2.38 (was used to download the datasets yahoo_bitcoin_data_2024-03-19.csv and yahoo_ex_rates_data_2024-03-19.csv, which is not necessary to reproduce the results)

## Metadata:
All metadata files follow the CSVW Namespace Vocabulary Terms for metadata from W3C and contains common metadata such as title, description and datatype. The vocabulary and term explanation is available at https://www.w3.org/ns/csvw.

