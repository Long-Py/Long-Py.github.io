---
layout: post
title: '709. To Lower Case'
subtitle: ''
date: 2019-08-08
categories: Leetcode
tags: Leetcode Strings
---

### [709\. To Lower Case](https://leetcode.com/problems/to-lower-case/)

Difficulty: **Easy**

Topics: **String**


Implement function ToLowerCase() that has a string parameter str, and returns the same string in lowercase.


**Example 1:**

```
Input: "Hello"
Output: "hello"
```

**Example 2:**

```
Input: "here"
Output: "here"
```

**Example 3:**

```
Input: "LOVELY"
Output: "lovely"
```

#### Solution

Language: **Python**

```python
class Solution(object):
    def toLowerCase(self, str):
        """
        :type str: str
        :rtype: str
        """
        return "".join(chr(ord(c) + 32) if 65 <= ord(c) <= 90 else c for c in str)
```

#### Notes
- Using `str.lower()` function is not good idea in an interview.
- Uppercase letters' ASCII code are from **65** ~ **90**;
   Lowercase letters' ASCII code are from **97** ~ **122**;
   The difference is **32**.
- The `ord()` method returns an integer representing Unicode code point for the given Unicode character.
- The `chr()` method returns a character (a string) from an integer (represents unicode code point of the character).