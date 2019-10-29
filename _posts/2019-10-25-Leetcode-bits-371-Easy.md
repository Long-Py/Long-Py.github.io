---
layout: post
title: '371. Sum of Two Integers'
subtitle: ''
date: 2019-10-25
categories: Leetcode
tags: Leetcode BitManipulation
---
### [371\. Sum of Two Integers](https://leetcode.com/problems/sum-of-two-integers/)

Difficulty: **Easy**

Topics: **Bit Manipulation**


Calculate the sum of two integers _a_ and _b_, but you are **not allowed** to use the operator `+` and `-`.


**Example 1:**

```
Input: a = 1, b = 2
Output: 3
```


**Example 2:**

```
Input: a = -2, b = 3
Output: 1
```


#### Solution

Language: **Python**

```python
class Solution(object):
    def getSum(self, a, b):
        """
        :type a: int
        :type b: int
        :rtype: int
        """
        # 32 bits integer max
        MAX = 0x7FFFFFFF
        # 32 bits interger min
        MIN = 0x80000000
        # mask to get last 32 bits
        mask = 0xFFFFFFFF
        while b != 0:
            # ^ get different bits and & gets double 1s, << moves carry
            a, b = (a ^ b) & mask, ((a & b) << 1) & mask
        # if a is negative, get a's 32 bits complement positive first
        # then get 32-bit positive's Python complement negative
        return a if a <= MAX else ~(a ^ mask)
```