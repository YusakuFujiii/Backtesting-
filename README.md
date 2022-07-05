# Backtesting-with-risk-exposure-controlled

### Problem setting 
Suppose that we have a nice-looking result in a backtest. The issue here is that the cumulative return might be achieved in the backtest with unrealistic amount of risk exposured. For instance, we have several positions at the same time, getting closer to a margin call. If that is the case, once we deploy the model, we fail. How can we do a backtest with risk exposure controlled?  

### Existing method developed by Yusaku Fujii
1. Execution based solely on a predefined max holding period  
   What is it? 
   - First, compute realized return at every timestamp based on a trading rule (called a primary model in AFML).
   - Second, set an arbitrary max holding period.
   - Third, extract the returns realized within the holding period. 
   - Lastly, regarding the case where returns are not realized within the period, we replace them with returns that are computed through a market exit order at the max holding  period. 

### Proposed method 
1. Conditional execution based on a current pl of a position and a predefined max holding period
   What is it?
   - This method basically follows the existig method above. 
   - The point is that unlike the existing one, even if returns are not realized within the period, if their pl is positive, we continue to hold that position. 
   What is good about it?
   - By using this method, we could avoid opportunity losses as much as possible. 
  


### Discussion
- For now, we prioritize not to exceed a max holding period (=the number of positions that we have at the same time). However, if the net pl of the positions is positive, we might want to let them go for a while. How can we implement the conditional execution? 
