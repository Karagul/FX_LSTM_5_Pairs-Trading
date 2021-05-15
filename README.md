# Pairs-Trading-With-LSTM

The aim of this project is to optimize the profit by trading the volatility of the spread of two co-integrated stocks, CCI and SBAC from S&P500, using LSTM prediction with normalized window.

Two main approaches were used:
* Adding the volatilities of other spreads as additional inputs
  1. The spreads with a third co-integrated stock AMT (CCI/AMT and SBAC/AMT) (denoted by **AMT**)
  2. The spreads of other co-integrated stocks from S&P500 (UNH/CNC and UNH/CI) (denoted by **OS**)
  3. The spreads with S&P500 itself (CCI/^GSPC and SBAC/^GSPC) (denoted by **ETF**)
* Modifing the LSTM algorithm
  1. Multi-layer LSTM with the activation function "tanh" (denoted by **LSTM 1**)
      
      <img src="https://github.com/quincyho/Pairs-Trading-With-LSTM/blob/main/Images/LSTM%201.PNG" width="200">
  3. Multi-layer LSTM with the activation function "relu" (denoted by **LSTM 2**)
      
      <img src="https://github.com/quincyho/Pairs-Trading-With-LSTM/blob/main/Images/LSTM%202.PNG" width="200">
  5. Bidirectional multi-layer LSTM with the activation function "relu" (denoted by **LSTM 3**)
  
      <img src="https://github.com/quincyho/Pairs-Trading-With-LSTM/blob/main/Images/LSTM%203.PNG" width="200">
  
*(Denotations for later expression convenience)*

The following table summarizes the input and LSTM configurations in each json file:

<img src="https://github.com/quincyho/Pairs-Trading-With-LSTM/blob/main/Images/Json%20reference.JPG" width="400">

The 2-days ahead long-only strategy is adopted to produce trading signals, i.e. if we know the predicted volatility after 2 days increases (predicted normalized volatility greater than 1), we go long.

After experimenting with different configurations, adding only the spreads other co-integrated stocks (**OS**) as additional inputs and using an unidirectional LSTM with the "relu" activation function (**LSTM 2**), i.e. config_9.json, produces the best result.

A compound annual growth rate (CAGR) of 581.7% and a Sharpe ratio of 1.0 were achieved with our trading signal, comparing to the market CAGR of -23.2% and the market Sharpe ratio of -0.1.

<img src="https://github.com/quincyho/Pairs-Trading-With-LSTM/blob/main/Images/CAGR%20and%20Sharpe.JPG" width="200">

Here are the plots from our program:
* MSE loss curve (training vs testing)

  <img src="https://github.com/quincyho/Pairs-Trading-With-LSTM/blob/main/Images/MSE%20Loss.png" width="500">
* Predicted volatility vs true volatility

  <img src="https://github.com/quincyho/Pairs-Trading-With-LSTM/blob/main/Images/Prediction.png" width="500">
* System equity curve vs market equity curve

  <img src="https://github.com/quincyho/Pairs-Trading-With-LSTM/blob/main/Images/Equity%20Curve.png" width="500">
