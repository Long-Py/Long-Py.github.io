---
layout: post
title: '461. Hamming Distance'
subtitle: ''
date: 2019-10-21
categories: Leetcode
tags: Leetcode BitManipulation
---
### [461\. Hamming Distance](https://leetcode.com/problems/hamming-distance/)

Difficulty: **Easy**

Topics: **Bit Manipulation**

The between two integers is the number of positions at which the corresponding bits are different.

Given two integers `x` and `y`, calculate the Hamming distance.

**Note:**  
0 ≤ `x`, `y` < 2<sup>31</sup>.

**Example:**

```
Input: x = 1, y = 4

Output: 2

Explanation:
1   (0 0 0 1)
4   (0 1 0 0)
       ↑   ↑

The above arrows point to positions where the corresponding bits are different.
```


#### Solution

Language: **Python**

```python
class Solution(object):
    def hammingDistance(self, x, y):
        """
        :type x: int
        :type y: int
        :rtype: int
        """
        tmp = x ^ y
        ans = 0
        while tmp > 0:
            ans += tmp & 1
            tmp >>= 1
        return ans
```