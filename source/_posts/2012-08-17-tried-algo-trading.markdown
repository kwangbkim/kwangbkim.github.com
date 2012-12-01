---
layout: post
title: "Tried Algo Trading, Losses Ensue"
date: 2012-08-26 18:06
comments: false
categories: [trading]
---
About a year ago I had some extra time on my hands and decided I'd take a crack at creating an [algorithmic trading](http://en.wikipedia.org/wiki/Algorithmic_trading) strategy.  [Interactive Brokers](http://individuals.interactivebrokers.com/en/main.php) offers an API which you can use to gather data and execute trades, though you will have to plop down the $10k minimum for an account.

Here's a quick pitch of the idea I was executing.  Long story short is that it did horribly, (maybe because I didn't want to make it do intraday trading, reason [here)](http://blogs.wsj.com/marketbeat/2012/08/02/knight-capital-trading-error-cost-firm-440-million/) but if you're interested in this stuff I've dumped all of my code out to [GitHub](https://github.com/kwangbkim/IBAlgoTrader).  

##Overview

On any given day most of the global markets are generally correlated.  Not only Asia/US/Europe, but emerging countries as well like Brazil and India.  But at the same time each individual country's financial market is affected by it's own inner dynamics.  Things like domestic and international politics can change a single economy in a way that differs from the rest of the world.

The idea is to track each individual country's market and compare it to some global world index.  I used Vanguard's [Total World Stock ETF](https://personal.vanguard.com/us/funds/snapshot?FundId=3141&FundIntExt=INT).  The price data I collected was daily and weekly.  By gathering price data based on different time intervals, I can calculate a country's correlation to the global index over multiple time periods.  When there's a large difference between the long term (weekly) and short term (daily) correlations, that denotes an event occurred in a particular country's domestic market and a trade should be made.

##Main pitfalls

* 	International events that affect multiple countries at the same time, triggering multiple trade alerts.  Not good because the goal is to make separate trades that are uncorrelated with each other to increase diversification and reduce variance.
*	It seemed like some events could just be rumors and dissipates quickly, or the market is just too efficient.  By the time my program noticed a correlation shift it would be too late and I'd lose money.

The true moral of the story here is that retail trading should be done for fun, not for profit!

