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

# Executive Summary
We can see that during the total duration of the simulation (from October 2021 - October 2024), the strategy has proven to be unprofitable. The total win rate percentage was 49.8%, with the total count of trades being 769, so it's a fairly large sample size. 

![image](https://github.com/user-attachments/assets/5f0c1127-6cec-49dd-850e-08ed8588ea12)



# Insights Deep Dive

# Recommendations

