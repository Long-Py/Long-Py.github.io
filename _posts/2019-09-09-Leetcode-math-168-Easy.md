---
layout: post
title: '168. Excel Sheet Column Title'
subtitle: ''
date: 2019-09-09
categories: Leetcode
tags: Leetcode Math
---
### [168\. Excel Sheet Column Title](https://leetcode.com/problems/excel-sheet-column-title/)

Difficulty: **Easy**

Topics: **Math**

Given a positive integer, return its corresponding column title as appear in an Excel sheet.

For example:

```
    1 -> A
    2 -> B
    3 -> C
    ...
    26 -> Z
    27 -> AA
    28 -> AB 
    ...
```

**Example 1:**

```
Input: 1
Output: "A"
```

**Example 2:**

```
Input: 28
Output: "AB"
```

**Example 3:**

```
Input: 701
Output: "ZY"
```


#### Solution

Language: **Python**

```python
class Solution(object):
    def convertToTitle(self, n):
        """
        :type n: int
        :rtype: str
        """
        ans = ''
        while n > 0:
            ans = chr((n-1)%26+65) + ans
            n = (n-1)//26
        return ans
```