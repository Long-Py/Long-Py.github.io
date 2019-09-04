---
layout: post
title: '171. Excel Sheet Column Number'
subtitle: ''
date: 2019-09-03
categories: Leetcode
tags: Leetcode Math
---
### [171\. Excel Sheet Column Number](https://leetcode.com/problems/excel-sheet-column-number/)

Difficulty: **Easy**

Topics: **Math**


Given a column title as appear in an Excel sheet, return its corresponding column number.

For example:

```
    A -> 1
    B -> 2
    C -> 3
    ...
    Z -> 26
    AA -> 27
    AB -> 28 
    ...
```

**Example 1:**

```
Input: "A"
Output: 1
```

**Example 2:**

```
Input: "AB"
Output: 28
```

**Example 3:**

```
Input: "ZY"
Output: 701
```


#### Solution

Language: **Python**

```python
class Solution(object):
    def titleToNumber(self, s):
        """
        :type s: str
        :rtype: int
        """
        idx = ans = 0
        for c in s[::-1]:
            ans += (ord(c)-ord('A') + 1)*(26**idx)
            idx += 1
        return ans
```