# Model Card

## Model Description

### Input: 
The model takes as input daily financial data including:

- Mexican Bolsa Index data: Close, Open, High, Low, Volume.
- Lagged data and returns.
- Technical indicators computed based on index data.
- VIX (Volatility Index of the S&P 500 Index, US) and previous day's changes.
- TIIE (Mexican Interbank Interest Rate) and previous day's changes.
- MXN (Mexican Peso exchange rate) and previous day's changes.

### Output: 
The model outputs a binary prediction indicating whether the next day's return for the Mexican Bolsa index will be positive (Buy signal) or negative (Sell signal).

### Model Architecture:

#### Simple Neural Network (SimpleANN): The network consists of:
   - An input layer with the same number of neurons as the number of input features.
   - A hidden layer with 30 neurons (best performing configuration).
   - An output layer with 1 neuron.
   - Activation functions: ReLU for the hidden layer and Sigmoid for the output layer.

## Performance

### Metrics:

Test Accuracy: 52.07%
Test Class 0 Positives %: 46.75%
Test Class 1 Positives %: 57.30%
Train Time: 0.056041 seconds
Final Investment Amount: $1.778149
Annualized Return: 13.69%
Annualized Standard Deviation: 14.29%
Sharpe Ratio: 0.653406

###Summary:
The Simple Neural Network model has demonstrated a test accuracy of 52.07%, with a balanced performance in predicting both positive and negative returns. The investment strategy based on the model's predictions yields an annualized return of 13.69% with a Sharpe Ratio of 0.653406, indicating a reasonable risk-adjusted return.

### Performance Tables

Comparison vs other models

![Captura de pantalla 2024-07-28 a la(s) 15 32 05](https://github.com/user-attachments/assets/8107a23e-95f1-455c-9c82-73e6810605fc)

Top 10 Grid search combinations
![Captura de pantalla 2024-07-28 a la(s) 16 51 22](https://github.com/user-attachments/assets/4e223a27-99fc-401f-8764-9cfa0d22d33c)

## Limitations

- Data Dependency: The model's performance heavily relies on the quality, quantity and accuracy of the input data. Any inaccuracies or missing data can significantly impact predictions.
- Market Conditions: The model is trained on historical data and may not generalize well to future market conditions, especially during unprecedented events. I notice this specially in behavior over COVID-19 times (already in test / out of sample set) where all models had a very volatile performances
- Overfitting: Despite cross-validation efforts, the model continues showing overfitting, particularly due to the complexity of financial markets, not enough data, changing environments and potential noise in the data.

## Trade-offs

- Bias-Variance Trade-off: The model may exhibit high variance due to its capacity to capture complex patterns in the data, which could lead to overfitting. Conversely, reducing complexity might increase bias, reducing the model's ability to capture meaningful patterns.
- Computation Time vs. Model Complexity: Increasing the number of neurons or layers in the neural network can enhance performance but at the cost of increased computation time and resource usage. A balance must be struck based on available computational resources.
- Feature Reduction: Using PCA and reduced feature sets may simplify the model and reduce overfitting but might also discard potentially valuable information, impacting model performance. This is aleady tested in the code but still requires further work

