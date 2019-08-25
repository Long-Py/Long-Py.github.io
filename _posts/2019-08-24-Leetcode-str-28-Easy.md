---
layout: post
title: '28. Implement strStr()'
subtitle: ''
date: 2019-08-24
categories: Leetcode
tags: Leetcode Strings
---
### [28\. Implement strStr()](https://leetcode.com/problems/implement-strstr/)

Difficulty: **Easy**

Topics: **Strings**


Implement .

Return the index of the first occurrence of needle in haystack, or **-1** if needle is not part of haystack.

**Example 1:**

```
Input: haystack = "hello", needle = "ll"
Output: 2
```

**Example 2:**

```
Input: haystack = "aaaaa", needle = "bba"
Output: -1
```

**Clarification:**

What should we return when `needle` is an empty string? This is a great question to ask during an interview.

For the purpose of this problem, we will return 0 when `needle` is an empty string. This is consistent to C's  and Java's .


#### Solution

Language: **Python**

```python
class Solution(object):
    def strStr(self, haystack, needle):
        """
        :type haystack: str
        :type needle: str
        :rtype: int
        """
        if not needle: return 0
        l = len(haystack)
        n = len(needle)
        for i in range(l-n+1):
            if haystack[i:i+n] == needle:
                return i
            
        return -1
```

#### Notes
- time complexity: O(m*n)