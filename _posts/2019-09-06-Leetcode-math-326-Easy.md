---
layout: post
title: '326. Power of Three'
subtitle: ''
date: 2019-09-06
categories: Leetcode
tags: Leetcode Math
---
### [326\. Power of Three](https://leetcode.com/problems/power-of-three/)

Difficulty: **Easy**

Topics: **Math**

Given an integer, write a function to determine if it is a power of three.

**Example 1:**

```
Input: 27
Output: true
```

**Example 2:**

```
Input: 0
Output: false
```

**Example 3:**

```
Input: 9
Output: true
```

**Example 4:**

```
Input: 45
Output: false
```

**Follow up:**  
Could you do it without using any loop / recursion?


#### Solution

Language: **Python**

```python
class Solution(object):
    def isPowerOfThree(self, n):
        """
        :type n: int
        :rtype: bool
        """
        if n < 1: return False
        while n > 1:
            if n%3 != 0:
                return False
            n //= 3
        return True
```