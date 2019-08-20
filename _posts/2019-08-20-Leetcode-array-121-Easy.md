---
layout: post
title: '121. Best Time to Buy and Sell Stock'
subtitle: ''
date: 2019-08-20
categories: Leetcode
tags: Leetcode Array
---
### [121\. Best Time to Buy and Sell Stock](https://leetcode.com/problems/best-time-to-buy-and-sell-stock/)

Difficulty: **Easy**

Topics: **Array**

Say you have an array for which the _i_<sup>th</sup> element is the price of a given stock on day _i_.

If you were only permitted to complete at most one transaction (i.e., buy one and sell one share of the stock), design an algorithm to find the maximum profit.

Note that you cannot sell a stock before you buy one.

**Example 1:**

```
Input: [7,1,5,3,6,4]
Output: 5
Explanation: Buy on day 2 (price = 1) and sell on day 5 (price = 6), profit = 6-1 = 5.
             Not 7-1 = 6, as selling price needs to be larger than buying price.
```

**Example 2:**

```
Input: [7,6,4,3,1]
Output: 0
Explanation: In this case, no transaction is done, i.e. max profit = 0.
```


#### Solution

Language: **Python**

```python
class Solution(object):
    def maxProfit(self, prices):
        """
        :type prices: List[int]
        :rtype: int
        """
        if len(prices) < 2: return 0
        min0 = prices[0]
        ans = 0
        for n in prices:
            if n > min0:
                ans = max(ans,n-min0)
            else:
                min0 = n
        return ans
```

#### Notes
- keep tracking the min price in the list, when price if higher than min price, update the result.
- notice: **edge case**