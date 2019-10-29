---
layout: post
title: '342. Power of Four'
subtitle: ''
date: 2019-10-28
categories: Leetcode
tags: Leetcode BitManipulation
---

### [342\. Power of Four](https://leetcode.com/problems/power-of-four/)

Difficulty: **Easy**

Topics: **Bit Manipulation**

Given an integer (signed 32 bits), write a function to check whether it is a power of 4.

**Example 1:**

```
Input: 16
Output: true
```


**Example 2:**

```
Input: 5
Output: false
```


**Follow up**: Could you solve it without loops/recursion?


#### Solution

Language: **Python**

```python
class Solution(object):
    def isPowerOfFour(self, num):
        """
        :type num: int
        :rtype: bool
        """
        # 0x55555555 is to get rid of those power of 2 but not power of 4
        # so that the single 1 bit always appears at the odd position 
        return num != 0 and num & (num - 1) == 0 and num & 0x55555555 != 0
```