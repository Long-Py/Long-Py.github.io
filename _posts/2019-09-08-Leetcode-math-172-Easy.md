---
layout: post
title: '172. Factorial Trailing Zeroes'
subtitle: ''
date: 2019-09-08
categories: Leetcode
tags: Leetcode Math
---
### [172\. Factorial Trailing Zeroes](https://leetcode.com/problems/factorial-trailing-zeroes/)

Difficulty: **Easy**

Topics: **Math**

Given an integer _n_, return the number of trailing zeroes in _n_!.

**Example 1:**

```
Input: 3
Output: 0
Explanation: 3! = 6, no trailing zero.
```

**Example 2:**

```
Input: 5
Output: 1
Explanation: 5! = 120, one trailing zero.
```

**Note:** Your solution should be in logarithmic time complexity.


#### Solution

Language: **Python**

```python
class Solution(object):
    def trailingZeroes(self, n):
        """
        :type n: int
        :rtype: int
        """
        return 0 if n == 0 else n / 5 + self.trailingZeroes(n / 5)
```
#### Notes
- find number of five
- time complexity: O(log<sub>5</sub><sup>n</sup>)