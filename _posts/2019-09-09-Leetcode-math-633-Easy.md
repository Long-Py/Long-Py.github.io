---
layout: post
title: '633. Sum of Square Numbers'
subtitle: ''
date: 2019-09-09
categories: Leetcode
tags: Leetcode Math
---
### [633\. Sum of Square Numbers](https://leetcode.com/problems/sum-of-square-numbers/)

Difficulty: **Easy**

Topics: **Math**


Given a non-negative integer `c`, your task is to decide whether there're two integers `a` and `b` such that a<sup>2</sup> + b<sup>2</sup> = c.

**Example 1:**

```
Input: 5
Output: True
Explanation: 1 * 1 + 2 * 2 = 5
```

**Example 2:**

```
Input: 3
Output: False
```


#### Solution

Language: **Python**

```python
class Solution(object):
    def judgeSquareSum(self, c):
        """
        :type c: int
        :rtype: bool
        """
        max_v, min_v = int(math.sqrt(c)), 0
        
        while max_v>=min_v:
            if c == max_v**2 + min_v**2:
                return True
            elif max_v**2 + min_v**2>c:
                max_v -= 1
            else:
                min_v += 1
        return False
```

#### Notes
- binary search, time complexity: O(sqrt(c)*logc)