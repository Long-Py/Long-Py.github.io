---
layout: post
title: '242. Valid Anagram'
subtitle: ''
date: 2019-08-28
categories: Leetcode
tags: Leetcode Strings HashTable Sort
---
### [242\. Valid Anagram](https://leetcode.com/problems/valid-anagram/)

Difficulty: **Easy**

Topics: **HashTable**


Given two strings _s_ and _t _, write a function to determine if _t_ is an anagram of _s_.

**Example 1:**

```
Input: s = "anagram", t = "nagaram"
Output: true
```

**Example 2:**

```
Input: s = "rat", t = "car"
Output: false
```

**Note:**  
You may assume the string contains only lowercase alphabets.

**Follow up:**  
What if the inputs contain unicode characters? How would you adapt your solution to such case?


#### Solution

Language: **Python**

```python
class Solution(object):
    def isAnagram(self, s, t):
        """
        :type s: str
        :type t: str
        :rtype: bool
        """
        if len(s) != len(t): return False
        d = {}
        for c in s:
            d[c] = d.get(c,0) + 1
        for c in t:
            if c not in d or d[c] == 0:
                return False
            d[c] -= 1
        return True
            
```
#### Notes
- notice: `if len(s) != len(t): return False`