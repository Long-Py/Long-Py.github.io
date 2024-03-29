---
layout: post
title: '392. Is Subsequence'
subtitle: ''
date: 2019-09-11
categories: Leetcode
tags: Leetcode BinarySearch DP Greedy
---
### [392\. Is Subsequence](https://leetcode.com/problems/is-subsequence/)

Difficulty: **Easy**

Topics: **Binary Search**


Given a string **s** and a string **t**, check if **s** is subsequence of **t**.

You may assume that there is only lower case English letters in both **s** and **t**. **t** is potentially a very long (length ~= 500,000) string, and **s** is a short string (<=100).

A subsequence of a string is a new string which is formed from the original string by deleting some (can be none) of the characters without disturbing the relative positions of the remaining characters. (ie, `"ace"` is a subsequence of `"abcde"` while `"aec"` is not).

**Example 1:**  
**s** = `"abc"`, **t** = `"ahbgdc"`

Return `true`.

**Example 2:**  
**s** = `"axc"`, **t** = `"ahbgdc"`

Return `false`.

**Follow up:**  
If there are lots of incoming S, say S1, S2, ... , Sk where k >= 1B, and you want to check one by one to see if T has its subsequence. In this scenario, how would you change your code?


#### Solution

Language: **Python**

```python
class Solution(object):
    def isSubsequence(self, s, t):
        """
        :type s: str
        :type t: str
        :rtype: bool
        """
        if not t and not s:
            return True
        if not t:
            return False
        if not s:
            return True
        for c in s:
            i = t.find(c)
            if i == -1:
                return False
            t = t[i+1:]
                
        return True
```
#### Notes
- time complexity: O(s*t)