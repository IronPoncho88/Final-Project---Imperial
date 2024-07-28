# Datasheet 

## Motivation

The dataset was created to develop and test various machine learning (ML) models aimed at generating Buy/Sell signals for the Mexican Bolsa index. The purpose is to leverage daily public data, technical indicators, and fundamental data to predict the next day's returns for the index, which will subsequently inform an investment strategy designed to optimize returns. This project aims to demonstrate the potential of machine learning in making informed trading decisions in financial markets.

## Composition

- Instances Representation: The dataset comprises daily financial data, including index prices, volumes, interest rates, currency exchange rates, and volatility indices.
- Types of Instances:
  * Mexican Bolsa Index data (Close, Open, High, Low, Volume)
  * Lagged data, returns, and computed technical indicators
  * VIX (Volatility Index of the S&P 500 Index, US)
  * TIIE (Mexican Interbank Interest Rate)
  * MXN (Mexican Peso exchange rate)
- Number of Instances: after pre-processing, the final data set is approximately 5500 daily observations from 2002 to 2024.
- Missing Data: after pre-processing there is no missing data in the dataset.
- Confidential Data: The dataset does not contain any data that might be considered confidential as it is compiled from public sources.

## Collection process

#### Data Acquisition:
- Mexican Bolsa Index data: Acquired from Yahoo Finance.
- VIX data: Acquired from Yahoo Finance.
- TIIE data: Acquired from the Banxico webpage (Mexican Central Bank).
- MXN data: Acquired from Yahoo Finance.

- Sampling Strategy: The dataset is a comprehensive collection of daily observations over the specified time period, not a sample.

- Time Frame: The data spans from 2002 to 2024.

## Preprocessing/cleaning/labelling

- There is a processing of a raw and longer database that is shared in this repository.
- Database was larger but not all data was available (Volume) for longer tenors. The final database starts in 2002 after making sure all features have available data
- NaN, negatives or erroneus (#) data was removed by removing fully some specific dates where one of the inputs wasnt available due to holiday or non open markets in some asset classes.
- Technical indicators and lagged data were computed within the code using the index data.
- Daily changes in FX, VIX and TIIE were calculated.

Raw Data: The raw data was saved alongside the preprocessed data to support future uses and potential reprocessing.

## Uses

- Potential Tasks: The dataset could be used for a variety of financial modeling tasks, including but not limited to stock price prediction, volatility forecasting, and trading strategy development.

- Future Uses Impact: The composition of the dataset, being financial in nature, means that future uses must consider the inherent market risks and the potential for overfitting models to historical data. Users should be aware of the risk of developing models that may not generalize well to future data.

- Mitigation of Risks: Users can mitigate risks by performing robust out-of-sample testing, applying regularization techniques, and conducting thorough cross-validation.

- Inappropriate Uses: The dataset should not be used for tasks unrelated to financial markets or trading, such as predicting non-financial outcomes.
- 
## Distribution

The dataset is compiled from public sources and is subject to the terms of use of the respective data providers (e.g., Yahoo Finance, Banxico).

## Maintenance

The dataset is maintained by the project team responsible for the machine learning models. Future updates to the dataset will depend on the availability of new data from the original sources.


