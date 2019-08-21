---
layout: post
title: '415. Add Strings'
subtitle: ''
date: 2019-08-21
categories: Leetcode
tags: Leetcode Strings
---
### [415\. Add Strings](https://leetcode.com/problems/add-strings/)

Difficulty: **Easy**

Topics: **Strings**


Given two non-negative integers `num1` and `num2` represented as string, return the sum of `num1` and `num2`.

**Note:**

1.  The length of both `num1` and `num2` is < 5100.
2.  Both `num1` and `num2` contains only digits `0-9`.
3.  Both `num1` and `num2` does not contain any leading zero.
4.  You **must not use any built-in BigInteger library** or **convert the inputs to integer** directly.


#### Solution

Language: **Python**

```python
class Solution(object):
    def addStrings(self, num1, num2):
        """
        :type num1: str
        :type num2: str
        :rtype: str
        """
        carry = 0
        l1 = len(num1)-1
        l2 = len(num2)-1
        ans = ''
        while l1 >= 0 and l2>=0:
            s = int(num1[l1]) + int(num2[l2]) + carry
            carry = s//10
            ans = str(s%10) + ans
            l1 -= 1
            l2 -= 1
        while l1 >= 0:
            s = int(num1[l1]) + carry
            carry = s//10
            ans = str(s%10) + ans
            l1 -= 1  
        while l2 >= 0:
            s = int(num2[l2]) + carry
            carry = s//10
            ans = str(s%10) + ans
            l2 -= 1             
        if carry != 0:
            ans = str(carry) + ans
        return ans
```
#### Notes
- variable *carry* carrys 1 when sum is greater than 10
- calc from back to front