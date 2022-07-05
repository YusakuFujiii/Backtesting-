# Backtesting-with-risk-exposure-controlled

### Problem setting 
Suppose that we have a nice-looking result in a backtest. The issue here is that the cumulative return might be achieved in the backtest with unrealistic amount of risk exposured. For instance, we have several positions at the same time, getting closer to a margin call. If that is the case, once we deploy the model, we fail. How can we do a backtest with risk exposure controlled?  

### Existing method developed by Yusaku Fujii

1. Compute realized return at every timestamp based on a trading rule (called a primary model in AFML).
2. Set an arbitrary max holding period.
3. Extract the returns realized within the holding period. 
4. Regarding the case where returns are not realized within the period, we replace them with returns that are computed through a market exit order at the max holding period. 

### Proposed method 


### Discussion
- For now, we prioritize not to exceed a max holding period (=the number of positions that we have at the same time). However, if the net pl of the positions is positive, we might want to let them go for a while. How can we implement the conditional execution? 
