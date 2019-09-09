---
layout: post
title: '69. Sqrt(x)'
subtitle: ''
date: 2019-09-09
categories: Leetcode
tags: Leetcode Math
---
### [69\. Sqrt(x)](https://leetcode.com/problems/sqrtx/)

Difficulty: **Easy**

Topics: **Math**


Implement `int sqrt(int x)`.

Compute and return the square root of _x_, where _x_ is guaranteed to be a non-negative integer.

Since the return type is an integer, the decimal digits are truncated and only the integer part of the result is returned.

**Example 1:**

```
Input: 4
Output: 2
```

**Example 2:**

```
Input: 8
Output: 2
Explanation: The square root of 8 is 2.82842..., and since 
             the decimal part is truncated, 2 is returned.
```


#### Solution

Language: **Python**

```python
class Solution(object):
    def mySqrt(self, x):
        """
        :type x: int
        :rtype: int
        """
        ans = 0
        diff = float('inf')
        l, r = 0, x
        while l <= r:
            mid = (l+r)//2
            if mid*mid == x:
                return mid
            elif mid*mid < x:
                if x - mid*mid < diff:
                    diff = x - mid*mid
                    ans = mid
                l = mid + 1
            else:
                r = mid - 1
        return ans
```

#### Notes
- binary search