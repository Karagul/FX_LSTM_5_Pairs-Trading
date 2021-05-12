# Pairs-Trading-With-LSTM

The aim of this project is to optimize the profit by trading the volatility of the spread of two co-integrated stocks, CCI and SBAC from S&P500, with LSTM prediction.

Two main approaches were adopted:
* Adding the volatilities of other spreads as inputs
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
