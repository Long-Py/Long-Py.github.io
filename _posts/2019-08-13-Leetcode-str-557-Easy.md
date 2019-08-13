---
layout: post
title: '557. Reverse Words in a String III'
subtitle: ''
date: 2019-08-13
categories: Leetcode
tags: Leetcode Strings
---
### [557\. Reverse Words in a String III](https://leetcode.com/problems/reverse-words-in-a-string-iii/)

Difficulty: **Easy**

Topics: **String**


Given a string, you need to reverse the order of characters in each word within a sentence while still preserving whitespace and initial word order.

**Example 1:**  

```
Input: "Let's take LeetCode contest"
Output: "s'teL ekat edoCteeL tsetnoc"
```

**Note:** In the string, each word is separated by single space and there will not be any extra space in the string.


#### Solution

Language: **Python**

```python
class Solution(object):
    def reverseWords(self, s):
        """
        :type s: str
        :rtype: str
        """
        return " ".join(a[::-1] for a in s.split())
```

#### Notes
- The `join()` method takes all items in an iterable and joins them into one string.
A string must be specified as the **separator**.