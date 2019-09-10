---
layout: post
title: '7. Reverse Integer'
subtitle: ''
date: 2019-09-09
categories: Leetcode
tags: Leetcode Math
---
### [7\. Reverse Integer](https://leetcode.com/problems/reverse-integer/)

Difficulty: **Easy**

Topics: **Math**

Given a 32-bit signed integer, reverse digits of an integer.

**Example 1:**

```
Input: 123
Output: 321
```

**Example 2:**

```
Input: -123
Output: -321
```

**Example 3:**

```
Input: 120
Output: 21
```

**Note:**  
Assume we are dealing with an environment which could only store integers within the 32-bit signed integer range: [−2<sup>31</sup>,  2<sup>31 </sup>− 1]. For the purpose of this problem, assume that your function returns 0 when the reversed integer overflows.


#### Solution

Language: **Python**

```python
class Solution(object):
    def reverse(self, x):
        """
        :type x: int
        :rtype: int
        """
        cur = abs(x)
        ans = 0
        while cur > 0:
            ans *= 10
            ans += cur%10
            cur //= 10
        if x < 0: 
            ans = -1 * ans
        if ans > 2**31-1 or ans < -1 * 2**31:
            return 0
        else:
            return ans
            ans = -1 * ans
```