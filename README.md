# Pairs-Trading-With-LSTM

The aim of this project is to optimize the profit by trading the volatility of the spread of two co-integrated stocks, CCI and SBAC from S&P500, with LSTM prediction.

Two main approaches were adopted:
* Adding the volatilities of other spreads as inputs
  1. The spreads with a third co-integrated stock AMT (CCI/AMT and SBAC/AMT) (denoted by **AMT**)
  2. The spreads of other co-integrated stocks from S&P500 (UNH/CNC and UNH/CI) (denoted by **OS**)
  3. The spreads with S&P500 itself (CCI/^GSPC and SBAC/^GSPC) (denoted by **ETF**)
* Modifing the LSTM algorithm
  1. Multi-layer LSTM with the activation function "tanh" (denoted by **LSTM 1**)
  2. Multi-layer LSTM with the activation function "relu" (denoted by **LSTM 2**)
  3. Bidirectional multi-layer LSTM with the activation function "relu" (denoted by **LSTM 3**)
  
*(Denotations for later expression convenience)*
