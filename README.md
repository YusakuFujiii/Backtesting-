# Backtesting-with-risk-exposure-controlled

### Problem setting 
Suppose that we have a nice-looking result in a backtest. The issue here is that the cumulative return might be achieved in the backtest with unrealistic amount of risk exposured. For instance, we have several positions at the same time, getting closer to a margin call. If that is the case, once we deploy the model, we fail. How can we do a backtest with risk exposure controlled?  

### Existing method developed by Yusaku Fujii
Execution based solely on a predefined max holding period  

What is it? 
   - First, compute realized return at every timestamp based on a trading rule (called a primary model in AFML).
   - Second, set an arbitrary max holding period.
   - Third, extract the returns realized within the holding period. 
   - Lastly, regarding the case where returns are not realized within the period, we replace them with returns that are computed through a market exit order at the max holding  period. 

### Further research 

