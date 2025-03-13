# Background and Overview
Mechanical trading strategies is a highly controversial topic in the trading community, especially in futures trading. To start off, let me define a mechanical vs discretionary strategy. 

A mechanical strategy is when the trader has a list of parameters, a checklist of some sort, that is based off of **technical** analysis, typically from technical calculations done by indicators. The trader does not need to make any decision, the entry is purely determined by the technical indicators and whether they meed certain criteria. 

A discretionary strategy is when the trader uses their personal interpretation of the market to decide whether to enter or not. Typically a trader will also use technical calculations done by indicators, but only in addition to their own analysis done through their interpretation of what information the market is providing them. The decision to enter the trade is entirely up to the traders discretion. 

People will swear by automated strategies, some people swear by purely discretionary strategies. A member of Banana Bread Trades discord community, a community of over 1000+ traders, sought the opinion of other traders on a new mechanical strategy he had found from another trader. The trading strategy is called: the 5 minute opening range breakout strategy. As the name suggests, after the first 5 minutes of market open (market opens at 9:30 AM), a trade will be taken in the direction that price breaks out of. Observe the following graphic:
![image](https://github.com/user-attachments/assets/1904da44-94b8-47bf-b07a-7d4087d191b2)

If price first breaks the high, the trader will be entered in a long, betting that price will go higher. The take profit is the # of points that the opening range size is. So if the opening range size is 5 points, and the trader enters into a long at a price of 10,000, the take profit for the trade is at 10,005, and the stop loss is at 9,990, the other side of the opening range.

The trader who sought the opinion of others wanted to know if it was a strategy worth using. Since it is a purely mechanical strategy, it can be coded and back-tested, which I offered to do for him. 
We wanted to know the following:
- Has the strategy been profitable?
- Is the strategy overly risky? That is, are the stop sizes too large to risk, given that traders can only accumulate so much drawdown.
- Is there a bias to longs being more profitable than shorts? This can help determine filters to apply to the strategy to decrease losses and increase win rate %.

# Data Structure Overview
The data given to me was in the following format:

![image](https://github.com/user-attachments/assets/eb9b4a0c-8968-4b6f-ba56-481352192179)

Much of the data had to be reformatted, especially column names, and the datetime formats. Additional labels were applied to rows to categorize candlestick data by session, for trade scripting to be easier. 

A script that I created then took all of this candlestick data from the past 3 years, and ran trade simulations, converting it into a table with this structure:

![image](https://github.com/user-attachments/assets/89db1010-578d-41bf-be42-240fb50d8b34)

# Executive Summary
We can see that during the total duration of the simulation (from October 2021 - October 2024), the strategy has proven to be unprofitable. The **total win rate percentage was 49.8%**, with the **total count of trades being 769**, so it's a fairly large sample size. Over time, it **netted a loss of 554 points**, which is actually not alot, considering that the distribution of points wagered per trade is centered around 40-50, with a tail to the higher side, meaning that the difference from -554 points to 0 points could have been a mere 10-15 trades. We can also see that **the long and short winrate in total were both 50%,** and both show **no significant PnL trends or changes in the RR distribution**. So while there may be reasons to consider this strategy a breakeven strategy at best, most signs point to it being **unreliable, and having no greater edge in the market than a coin flip**. Specific trending periods are analyzed in the following section, and the entire interactive dashboard can be downloaded [here](https://github.com/Saatvik1/Futures-Market-Analysis/blob/main/Analysis/NQ/Zanek5Breakout/IntermediateData/5MORB_Analysis.pbix).

![image](https://github.com/user-attachments/assets/5f0c1127-6cec-49dd-850e-08ed8588ea12)
![image](https://github.com/user-attachments/assets/de2fd626-cb9b-4887-a933-d59a73701caf)
![image](https://github.com/user-attachments/assets/3ac7556a-d0cb-499a-8cec-5fd395a668cc)



# Insights Deep Dive
So we have ruled out using this strategy as a standalone strategy. Is there anything that can be done to turn it from a coinflip and at best breakeven strategy to a winning strategy with real edge in the market? To answer this question I wanted to dig a little deeper into the data, trying to uncover any aspects that would show that certain conditions of the strategy tend to be more profitable. 
### Questions like:
- If we break out of the 5 minute opening range later than usual, does that mean a more directional move is more likely, giving us a better chance of winning? If so, we can apply a time filter to our strategy to increase the win %.
- Do the larger trades (larger Risk/Reward (RR)) the main causes of our losses? If so, we can apply a filter, so that we DON'T take trades if the opening range candle is larger than X points.
- If the market is trending a certain direction, will the momentum from this trend cause a trend in win rate increasing? In other words, is there an element of periodicity in the strategy, and can we observe this, and find a correlation and causation to better this strategy?

### Question 1: 
I applied the win and loss filter to observe the weight of win loss frequencies, and how they change by time.

![image](https://github.com/user-attachments/assets/71f6aad8-3945-4510-b7d7-e60e74aec9da) ![image](https://github.com/user-attachments/assets/aaf09560-1b6e-46ae-86f3-1e6cc09591ce)![image](https://github.com/user-attachments/assets/227f3ae2-97c6-49c0-a4b8-960d57dd1b61)

As we can see here, there is essentially no difference in time entry and exit distribution when filtering by winning and losing trades. In addition, **only 14% of all trades did not occur immediately** after the opening range was established, and this pattern seems to be fairly distributed among the entirety of the 3 years. This means that **applying a time filter will prove to be ineffective**, as the # of trades taken will diminish greatly, **with no significant positive return to justify doing so**. 

### Question 2:





# Recommendations

