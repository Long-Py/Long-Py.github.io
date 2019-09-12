---
layout: post
title: '70. Climbing Stairs'
subtitle: ''
date: 2019-09-12
categories: Leetcode
tags: Leetcode DP
---
### [70\. Climbing Stairs](https://leetcode.com/problems/climbing-stairs/)

Difficulty: **Easy**

Topics: **DP**

You are climbing a stair case. It takes _n_ steps to reach to the top.

Each time you can either climb 1 or 2 steps. In how many distinct ways can you climb to the top?

**Note:** Given _n_ will be a positive integer.

**Example 1:**

```
Input: 2
Output: 2
Explanation: There are two ways to climb to the top.
1\. 1 step + 1 step
2\. 2 steps
```

**Example 2:**

```
Input: 3
Output: 3
Explanation: There are three ways to climb to the top.
1\. 1 step + 1 step + 1 step
2\. 1 step + 2 steps
3\. 2 steps + 1 step
```


#### Solution

Language: **Python**

```python
class Solution(object):
    def climbStairs(self, n):
        """
        :type n: int
        :rtype: int
        """
        a, b = 0, 1
        for _ in range(n+1):
            a, b = b, a+b
        return a
```