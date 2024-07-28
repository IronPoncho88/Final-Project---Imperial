# BUY / SELL SIGNALS FOR THE MEXICAN EQUITY INDEX
#### Imperial College - ML & AI - Final Project

## NON-TECHNICAL EXPLANATION OF YOUR PROJECT
This project aims to test various ML models to generate Buy/Sell signals for the Mexican Bolsa index. These models utilize daily public data, technical indicators, and basic data on the Mexican currency, interest rates, and the VIX (US Volatility Index) for market sentiment. The objective is to predict positive or negative returns for the following day in the index. Based on these predictions, an investment strategy will be developed to capitalize on the forecasted movements. This approach seeks to optimize returns by leveraging machine learning to make informed trading decisions.

## DATA
All data is daily observed from 2002 to 2024 and all is coming from public sources
- Mexican Bolsa Index data: Close, Open, High, Low, Volume.
  - Source: Yahoo Finance
- Lagged data, returns and Index Technical Indicators: computed within the code based on Index data
  - Computed inside the model 
- VIX (Volatility Index of S&P500 Index - US -) and previous days changes
  - Source: Yahoo Finance
- TIIE (Mexican Interbank inerest rate) and previous days changes
  - Source: Banxico webpage - Mexican Central Bank 
- MXN (Mexican Currency - Mexican peso) and previous days changes
  - Source: Yahoo Finance
  
## MODEL 
The model used is a simple artificial neural network (ANN) defined by the class SimpleANN. This model consists of an input layer, one hidden layer, and an output layer. The hidden layer uses ReLU activation, while the output layer uses a sigmoid activation function. We chose this model because it provided the best test accuracy and one of the strongest investment strategy outputs compared to other models. However, further exploration is required to fully understand its performance and potential improvements.

Additionally, the Random Forest model was the next closest in performance, showing consistent good results. Both models alternated as the best performers depending on different data splits, indicating their robustness. Further exploration is also warranted in using PCA and reduced feature sets as inputs. In some iterations PCA shows enhanced results but still requires more detailed iterations.

## HYPERPARAMETER OPTIMSATION
Multiple combinations of hyperparameters were optimized for the simple neural network included:

hidden_dim: the number of neurons in the hidden layer (values tested: [5, 10, 30, 50])
optimizer: optimization algorithm (values tested: ['Adam', 'SGD'])
lr: learning rate (values tested: [.1, 0.01, 0.001, .0001])
batch_size: size of the mini-batches for training (values tested: [10, 16, 32])
epochs: number of training epochs (values tested: [10, 20, 30])
The optimal hyperparameters were determined through a manual grid search with time series cross-validation. The best parameters found were the following, but exploration wasn't exhaustive as I was doing comparisons VS many other models. Further refinement in hyperparameters is required.

batch_size: 16
epochs: 10
hidden_dim: 30
lr: 0.001
optimizer: Adam

## RESULTS
The simple neural network model achieved the following results:

Test Accuracy: 52.07% (vs 50.41% passive accuracy)
Test Class 0 Positives %: 46.75%
Test Class 1 Positives %: 57.30%
Training Time: 0.056 seconds
Final Investment Amount: 1.778149
Annualized Return: 0.136934 (vs .0409 and .082 of passive alway Buy and always Sell strategies)
Annualized Standard Deviation: 0.142921
Sharpe Ratio: 0.653406

You can include images of plots using the code below:
![Captura de pantalla 2024-07-28 a la(s) 15 32 05](https://github.com/user-attachments/assets/346ba010-f1fe-4245-b91d-8dcf2d61048d)


## (OPTIONAL: CONTACT DETAILS)
If you are planning on making your github repo public you may wish to include some contact information such as a link to your twitter or an email address. 

