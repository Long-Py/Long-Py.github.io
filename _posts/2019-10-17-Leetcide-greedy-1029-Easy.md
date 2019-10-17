---
layout: post
title: '1029. Two City Scheduling'
subtitle: ''
date: 2019-10-16
categories: Leetcode
tags: Leetcode Greedy Array
---
### [1029\. Two City Scheduling](https://leetcode.com/problems/two-city-scheduling/)

Difficulty: **Easy**

Topics: **Greedy**

There are `2N` people a company is planning to interview. The cost of flying the `i`-th person to city `A` is `costs[i][0]`, and the cost of flying the `i`-th person to city `B` is `costs[i][1]`.

Return the minimum cost to fly every person to a city such that exactly `N` people arrive in each city.

**Example 1:**

```
Input: [[10,20],[30,200],[400,50],[30,20]]
Output: 110
Explanation: 
The first person goes to city A for a cost of 10.
The second person goes to city A for a cost of 30.
The third person goes to city B for a cost of 50.
The fourth person goes to city B for a cost of 20.

The total minimum cost is 10 + 30 + 50 + 20 = 110 to have half the people interviewing in each city.
```

**Note:**

1.  `1 <= costs.length <= 100`
2.  It is guaranteed that `costs.length` is even.
3.  `1 <= costs[i][0], costs[i][1] <= 1000`


#### Solution

Language: **Python**

```python
class Solution(object):
    def twoCitySchedCost(self, costs):
        """
        :type costs: List[List[int]]
        :rtype: int
        """
        N = len(costs)//2
        ans = sum(i[0] for i in costs)
        diff = sorted([a-b for a,b in costs], reverse=True)
        return ans - sum(diff[:N])
        
```