---
layout: post
title: '290. Word Pattern'
subtitle: ''
date: 2019-08-29
categories: Leetcode
tags: Leetcode Strings HashTable
---
### [290\. Word Pattern](https://leetcode.com/problems/word-pattern/)

Difficulty: **Easy**

Topics: **HashTable**

Given a `pattern` and a string `str`, find if `str` follows the same pattern.

Here **follow** means a full match, such that there is a bijection between a letter in `pattern` and a **non-empty** word in `str`.

**Example 1:**

```
Input: pattern = "abba", str = "dog cat cat dog"
Output: true
```

**Example 2:**

```
Input:pattern = "abba", str = "dog cat cat fish"
Output: false
```

**Example 3:**

```
Input: pattern = "aaaa", str = "dog cat cat dog"
Output: false
```

**Example 4:**

```
Input: pattern = "abba", str = "dog dog dog dog"
Output: false
```

**Notes:**  
You may assume `pattern` contains only lowercase letters, and `str` contains lowercase letters that may be separated by a single space.


#### Solution

Language: **Python**

```python
class Solution(object):
    def wordPattern(self, pattern, str):
        """
        :type pattern: str
        :type str: str
        :rtype: bool
        """
        p = list(pattern)
        s = str.split()
        if len(p) != len(s): return False
        return len(set(zip(p,s))) == len(set(p)) == len(set(s))
```