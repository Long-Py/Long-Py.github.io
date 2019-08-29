---
layout: post
title: '205. Isomorphic Strings'
subtitle: ''
date: 2019-08-29
categories: Leetcode
tags: Leetcode Strings HashTable
---
### [205\. Isomorphic Strings](https://leetcode.com/problems/isomorphic-strings/)

Difficulty: **Easy**

Topics: **HashTable**


Given two strings **_s_** and **_t_**, determine if they are isomorphic.

Two strings are isomorphic if the characters in **_s_** can be replaced to get **_t_**.

All occurrences of a character must be replaced with another character while preserving the order of characters. No two characters may map to the same character but a character may map to itself.

**Example 1:**

```
Input: s = "egg", t = "add"
Output: true
```

**Example 2:**

```
Input: s = "foo", t = "bar"
Output: false
```

**Example 3:**

```
Input: s = "paper", t = "title"
Output: true
```

**Note:**  
You may assume both **_s _**and **_t _**have the same length.


#### Solution

Language: **Python**

```python
class Solution(object):
    def isIsomorphic(self, s, t):
        """
        :type s: str
        :type t: str
        :rtype: bool
        """
        return len(set(zip(s,t))) ==  len(set(s)) == len(set(t))
```