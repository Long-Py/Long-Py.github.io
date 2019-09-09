---
layout: post
title: '441. Arranging Coins'
subtitle: ''
date: 2019-09-08
categories: Leetcode
tags: Leetcode Math
---
### [441\. Arranging Coins](https://leetcode.com/problems/arranging-coins/)

Difficulty: **Easy**

Topics: **Math**


You have a total of _n_ coins that you want to form in a staircase shape, where every _k_-th row must have exactly _k_ coins.

Given _n_, find the total number of **full** staircase rows that can be formed.

_n_ is a non-negative integer and fits within the range of a 32-bit signed integer.

**Example 1:**

```
n = 5

The coins can form the following rows:
¤
¤ ¤
¤ ¤

Because the 3rd row is incomplete, we return 2.
```

**Example 2:**

```
n = 8

The coins can form the following rows:
¤
¤ ¤
¤ ¤ ¤
¤ ¤

Because the 4th row is incomplete, we return 3.
```


#### Solution

Language: **Python**

```python
class Solution(object):
    def arrangeCoins(self, n):
        """
        :type n: int
        :rtype: int
        """
        k = 1
        sum = 0
        while sum+k <= n:
            sum += k
            k += 1
        return k-1
```

#### Notes
- math method: `int((math.sqrt(8 * n + 1)-1)/2)`