---
layout: post
title:      "JavaScript Algos Pt. 5"
date:       2019-12-24 09:28:17 +0000
permalink:  javascript_algos_pt_5
---


How much money could I have made yesterday trading stocks? 

I'm writing a function that takes an input of stock prices and returns the best profit I could have made from one purchase and one sale of one share of Apple stock yesterday.

Ignoring all the finance.ie jargon, basically we're just taking an array input, then calculating what's the cheapest price (the lowest number in the arr) I could've bought the stock and the highest I could've sold it (the biggest number that appears *after* the lowest number in the arr). Do a little math, then return that profit. 

By recognizing that the Greedy algorithm is the way to go here, we can navigate any pesky edge cases, like when there's fewer than 2 stock prices and if there's no profit in a day.

The Greedy algorithm basically always picks the best possible solution at every step of the process. For example, if I was picking out chocolates from a box that I'm sharing with my brother (he gets one, I get one, etc), I would pick the largest chocolate available whenever it's my turn. That's the greedy algo approach in a nutshell/ cocoa shell.
<br>



```

function getMaxProfit(stockPrices) {

    // Calculate the max profit
    // Greedy algo: constantly compare the prev 2 ways 
    // update minPrice and maxProfit to initialize them as first price
    // and first possible profit 
    let maxProfit = stockPrices[1] - stockPrices[0];
    let minPrice = stockPrices[0];
    
    // Edge case
    if(stockPrices.length < 2) {
      return "We need at least 2 stock prices for a profit"
    }
    
    // Start at 2nd index to circumvent the issue of return 0 when 
    // maxProfit is negative. We can't sell at 0, so we'll start at 1
    for(let i = 1; i< stockPrices.length; i++) {
      const currentPrice = stockPrices[i];
      
      // What would be profit if we bought at min and sold at current? 
      const potentialProfit = currentPrice - minPrice
      
      // Update the maxProfit
      maxProfit = Math.max(maxProfit, potentialProfit);
      
      // Update minPrice so it's always the lowest we've seen 
      minPrice = Math.min(minPrice, currentPrice);
      
    }
    
    return maxProfit; 
    
}
  
 
getMaxProfit([10, 7, 5, 8, 11, 9]);
 
 
// Expected output: 6 from purchasing at 5 then selling at 11

```


Thanks for reading! <br>
Indy

