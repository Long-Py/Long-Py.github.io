---
layout: post
title: '367. Valid Perfect Square'
subtitle: ''
date: 2019-09-06
categories: Leetcode
tags: Leetcode Math
---
### [367\. Valid Perfect Square](https://leetcode.com/problems/valid-perfect-square/)

Difficulty: **Easy**

Topics: **Math**


Given a positive integer _num_, write a function which returns True if _num_ is a perfect square else False.

**Note:** **Do not** use any built-in library function such as `sqrt`.

**Example 1:**


```
Input: 16
Output: true
```


**Example 2:**

```
Input: 14
Output: false
```


#### Solution

Language: **Python**

```python
class Solution(object):
    def isPerfectSquare(self, num):
        """
        :type num: int
        :rtype: bool
        """
        l, r = 0, num
        while l <= r:
            m = l + (r-l)//2
            if m*m == num:
                return True
            elif m*m < num:
                l = m+1
            else:
                r = m-1
        return False
```
#### Notes
- binary search, time complexity: O(logn)