---
layout: post
title: '405. Convert a Number to Hexadecimal'
subtitle: ''
date: 2019-10-28
categories: Leetcode
tags: Leetcode BitManipulation
---
### [405\. Convert a Number to Hexadecimal](https://leetcode.com/problems/convert-a-number-to-hexadecimal/)

Difficulty: **Easy**

Topics: **Bit Manipulation**

Given an integer, write an algorithm to convert it to hexadecimal. For negative integer, method is used.

**Note:**

1.  All letters in hexadecimal (`a-f`) must be in lowercase.
2.  The hexadecimal string must not contain extra leading `0`s. If the number is zero, it is represented by a single zero character `'0'`; otherwise, the first character in the hexadecimal string will not be the zero character.
3.  The given number is guaranteed to fit within the range of a 32-bit signed integer.
4.  You **must not use _any_ method provided by the library** which converts/formats the number to hex directly.

**Example 1:**

```
Input:
26

Output:
"1a"
```

**Example 2:**

```
Input:
-1

Output:
"ffffffff"
```


#### Solution

Language: **Python**

```python
class Solution(object):
    def toHex(self, num):
        """
        :type num: int
        :rtype: str
        """
        if num==0: return '0'
        mp = '0123456789abcdef'  # like a map
        ans = ''
        for i in range(8):
            n = num & 15       # this means num & 1111b
            c = mp[n]          # get the hex char
            ans = c + ans
            num >>= 4
        return ans.lstrip('0')  #strip leading zeroes
            
```