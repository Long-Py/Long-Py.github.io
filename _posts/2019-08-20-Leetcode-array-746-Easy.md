---
layout: post
title: '746. Min Cost Climbing Stairs'
subtitle: ''
date: 2019-08-20
categories: Leetcode
tags: Leetcode Array DP
---

### [746\. Min Cost Climbing Stairs](https://leetcode.com/problems/min-cost-climbing-stairs/)

Difficulty: **Easy**

Topics: **Array**


On a staircase, the `i`-th step has some non-negative cost `cost[i]` assigned (0 indexed).

Once you pay the cost, you can either climb one or two steps. You need to find minimum cost to reach the top of the floor, and you can either start from the step with index 0, or the step with index 1.

**Example 1:**  

```
Input: cost = [10, 15, 20]
Output: 15
Explanation: Cheapest is start on cost[1], pay that cost and go to the top.
```

**Example 2:**  

```
Input: cost = [1, 100, 1, 1, 1, 100, 1, 1, 100, 1]
Output: 6
Explanation: Cheapest is start on cost[0], and only step on 1s, skipping cost[3].
```

**Note:**  

1.  `cost` will have a length in the range `[2, 1000]`.
2.  Every `cost[i]` will be an integer in the range `[0, 999]`.


#### Solution

Language: **Python**

```python
class Solution(object):
    def minCostClimbingStairs(self, cost):
        """
        :type cost: List[int]
        :rtype: int
        """
        
        if len(cost) < 2: return 0
        min1, min2 = cost[0], cost[1]
        for i in range(2,len(cost)):
            min1, min2 = min2, min(min1,min2)+cost[i]
        return min(min1,min2)
```

#### Notes
- DP: `f[i] = cost[i] + min(f[i+1], f[i+2])`