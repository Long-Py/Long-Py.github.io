---
layout: post
title: '459. Repeated Substring Pattern'
subtitle: ''
date: 2019-08-22
categories: Leetcode
tags: Leetcode Strings
---

### [459\. Repeated Substring Pattern](https://leetcode.com/problems/repeated-substring-pattern/)

Difficulty: **Easy**

Topics: **Strings**


Given a non-empty string check if it can be constructed by taking a substring of it and appending multiple copies of the substring together. You may assume the given string consists of lowercase English letters only and its length will not exceed 10000.

**Example 1:**

```
Input: "abab"
Output: True
Explanation: It's the substring "ab" twice.
```

**Example 2:**

```
Input: "aba"
Output: False
```

**Example 3:**

```
Input: "abcabcabcabc"
Output: True
Explanation: It's the substring "abc" four times. (And the substring "abcabc" twice.)
```


#### Solution

Language: **Python**

```python
class Solution(object):
    def repeatedSubstringPattern(self, s):
        """
        :type s: str
        :rtype: bool
        """
        return s in (2*s)[1:-1]
    
```
#### Notes
- This is idea can be also used to solve string rotate problem.