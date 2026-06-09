This backtest's goal is to measure the returns, drawdowns e expectancy of a simple trading strategy: mean-reversion using standards deviations from the 20 simple moving average. The idea first came from a gaussian distribuition, using the concept that 95% of data should be contained in 2 standard deviations and 99% should be contained in 3 standard devitaions. With that being said, with the market presents a candle close out of this two groups, i assume a reversion is near.\

It's going to be used the 2 and 3 standard deviations, to compare returns in a more frequenty scenario, but more likely to lose more times with a less frequenty one, but more extended from the 20 sma.\

The stop losses are going to be positioned in two ways: the first is going to be 1x the entry's candle atr and the second one just above the max if we're going to sell and just under the low if we're going to buy.\

The target (obviously) is the 20 simple moving average. Since i'm using a OHLC csv database, not a tick-tick type of data, a gain will be considered when the average's price be contained within a candle range assuming the candle reached the average's price.\

One important detail is: using a knowledge of technical analysis, all of this can be resumed in a bollinger band concept. For the technicians, we all know that when the bands are squezed, the market is more likely to explode and the bands to extends, meaning it's a scenario that we should play a momentum trade, not a mean-reversion one. So, to filter just the moments that the bands are expanded, i'll be using a high percentile of the median (70, 80, 90, 95) insted of just a historical mean to really filter the outliers closes outside the stds. 
