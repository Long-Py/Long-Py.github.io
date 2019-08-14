---
layout: post
title: '521. Longest Uncommon Subsequence I'
subtitle: ''
date: 2019-08-14
categories: Leetcode
tags: Leetcode Strings
---
### [521\. Longest Uncommon Subsequence I](https://leetcode.com/problems/longest-uncommon-subsequence-i/)

Difficulty: **Easy**

Topics: **Strings**

Given a group of two strings, you need to find the longest uncommon subsequence of this group of two strings. The longest uncommon subsequence is defined as the longest subsequence of one of these strings and this subsequence should not be **any** subsequence of the other strings.

A **subsequence** is a sequence that can be derived from one sequence by deleting some characters without changing the order of the remaining elements. Trivially, any string is a subsequence of itself and an empty string is a subsequence of any string.

The input will be two strings, and the output needs to be the length of the longest uncommon subsequence. If the longest uncommon subsequence doesn't exist, return -1.

**Example 1:**  

```
Input: "aba", "cdc"
Output: 3
Explanation: The longest uncommon subsequence is "aba" (or "cdc"), because "aba" is a subsequence of "aba", but not a subsequence of any other strings in the group of two strings. 
```

**Note:**

1.  Both strings' lengths will not exceed 100.
2.  Only letters from a ~ z will appear in input strings.


#### Solution

Language: **Python**

```python
class Solution(object):
    def findLUSlength(self, a, b):
        """
        :type a: str
        :type b: str
        :rtype: int
        """
        if a == b: return -1
        return max(len(a),len(b))
```
#### Notes
- This question is asking us to return the **longest** uncommon subsequance. There are only 2 scenarios: 
  1. a == b: return -1, as mentioned
  2. a != b: return the longer str, because we just need find the **longest** uncommon subsequence, don't over-thinking!!!