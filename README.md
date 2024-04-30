# Investigation of the Correlation Between the Bitcoin Price and Tortilla Prices in Mexico

\href{![image.png](https://zenodo.org/badge/DOI/10.5281/zenodo.11080415.svg)}{https://www.youtube.com/}

Tyler Vigen shows on his homepage (http://www.tylervigen.com) many examples of spurious correlations, which remind us that correlation does not imply causation. Inspired by his work, this project shows a further bizarre correlation between the Bitcoin price and the tortilla prices in Mexico.

The input for this project are three datasets. The first dataset contains the tortilla prices in Mexican Peso (MXN) for big retail stores and mom-and-pop stores for various states and cities in Mexico. The second dataset contains the daily closing prices of Bitcoin in US dollar (start date = ”2007-01-10”; end date = ”2024-02-28”). The third dataset contains the daily currency exchange rates, in order to convert the Mexican Peso (MXN) in the first dataset into US dollar (start date = ”2007-01-10”; end date = ”2024-02-28”). At the end, the output of this project are the Spearman correlation coefficients between the daily closing prices of Bitcoin and the mean tortilla prices for each state (aggregated over the prices per cities in the corresponding state) as well as separated for big retail stores and mom-and-pop stores.

## 1. Clone Repository and Install Requirements:
Clone this repository and run in your local repository: pip install -r requirements.txt

## 2. Download the Datasets:
