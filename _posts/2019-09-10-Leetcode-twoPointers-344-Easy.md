---
layout: post
title: '344. Reverse String'
subtitle: ''
date: 2019-09-10
categories: Leetcode
tags: Leetcode TwoPointers
---
### [344\. Reverse String](https://leetcode.com/problems/reverse-string/)

Difficulty: **Easy**

Topics: **Two Pointers**

Write a function that reverses a string. The input string is given as an array of characters `char[]`.

Do not allocate extra space for another array, you must do this by **modifying the input array ** with O(1) extra memory.

You may assume all the characters consist of .


**Example 1:**

```
Input: ["h","e","l","l","o"]
Output: ["o","l","l","e","h"]
```


**Example 2:**

```
Input: ["H","a","n","n","a","h"]
Output: ["h","a","n","n","a","H"]
```


#### Solution

Language: **Python**

```python
class Solution(object):
    def reverseString(self, s):
        """
        :type s: List[str]
        :rtype: None Do not return anything, modify s in-place instead.
        """
        l, r = 0, len(s)-1
        while l < r:
            s[l], s[r] = s[r], s[l]
            l += 1
            r -= 1
```