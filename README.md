# Backtesting-with-risk-exposure-controlled

### Problem setting 
Suppose that we have a nice-looking result in a backtest. The issue here is that the cumulative return might be achieved in the backtest with unrealistic amount of risk exposured. For instance, we have several positions at the same time, getting closer to a margin call. If that is the case, once we deploy the model, we fail. How can we do a backtest with risk exposure controlled?  

### Proposed method
1. Compute realized return at every timestamp based on a trading rule (called a primary model in AFML).
2. Set an arbitrary max holding period.
3. Extract the returns realized within the holding period and sum them up.


