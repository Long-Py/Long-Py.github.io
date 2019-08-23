---
layout: post
title: '67. Add Binary'
subtitle: ''
date: 2019-08-22
categories: Leetcode
tags: Leetcode Strings
---
### [67\. Add Binary](https://leetcode.com/problems/add-binary/)

Difficulty: **Easy**

Topics: **Strings**


Given two binary strings, return their sum (also a binary string).

The input strings are both **non-empty** and contains only characters `1` or `0`.

**Example 1:**

```
Input: a = "11", b = "1"
Output: "100"
```

**Example 2:**

```
Input: a = "1010", b = "1011"
Output: "10101"
```


#### Solution

Language: **Python**

```python
class Solution(object):
    def addBinary(self, a, b):
        """
        :type a: str
        :type b: str
        :rtype: str
        """
        la =len(a)-1
        lb = len(b)-1
        carry = 0
        ans = ''
        while la >= 0 and lb >= 0:
            s = int(a[la]) + int(b[lb]) + carry
            ans = str(s%2) + ans
            carry = s//2
            la -= 1
            lb -= 1
        while la >= 0:
            s = int(a[la])+carry
            ans = str(s%2) + ans
            carry = s//2
            la -= 1
        while lb >= 0:
            s = int(b[lb])+carry
            ans = str(s%2) + ans
            carry = s//2
            lb -= 1
        return ans if carry == 0 else str(carry)+ans
            ans = str(s%2) + ans
```

#### Notes
- like sum two **linked list**