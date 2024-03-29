---
layout: post
title: '263. Ugly Number'
subtitle: ''
date: 2019-09-06
categories: Leetcode
tags: Leetcode Math
---
### [263\. Ugly Number](https://leetcode.com/problems/ugly-number/)

Difficulty: **Easy**

Topics: **Math**


Write a program to check whether a given number is an ugly number.

Ugly numbers are **positive numbers** whose prime factors only include `2, 3, 5`.

**Example 1:**

```
Input: 6
Output: true
Explanation: 6 = 2 × 3
```

**Example 2:**

```
Input: 8
Output: true
Explanation: 8 = 2 × 2 × 2
```

**Example 3:**

```
Input: 14
Output: false 
Explanation: 14 is not ugly since it includes another prime factor 7.
```

**Note:**

1.  `1` is typically treated as an ugly number.
2.  Input is within the 32-bit signed integer range: [−2<sup>31</sup>,  2<sup>31 </sup>− 1].


#### Solution

Language: **Python**

```python
class Solution(object):
    def isUgly(self, num):
        """
        :type num: int
        :rtype: bool
        """
        if num <= 0:
            return False
        for x in [2, 3, 5]:
            while num % x == 0:
                num = num / x
        return num == 1        
```