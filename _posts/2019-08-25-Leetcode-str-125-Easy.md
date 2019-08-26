---
layout: post
title: '125. Valid Palindrome'
subtitle: ''
date: 2019-08-25
categories: Leetcode
tags: Leetcode Strings
---
### [125\. Valid Palindrome](https://leetcode.com/problems/valid-palindrome/)

Difficulty: **Easy**

Topics: **Strings**

Given a string, determine if it is a palindrome, considering only alphanumeric characters and ignoring cases.

**Note:** For the purpose of this problem, we define empty string as valid palindrome.

**Example 1:**

```
Input: "A man, a plan, a canal: Panama"
Output: true
```

**Example 2:**

```
Input: "race a car"
Output: false
```


#### Solution

Language: **Python**

```python
class Solution(object):
    def isPalindrome(self, s):
        """
        :type s: str
        :rtype: bool
        """
        s = s.lower().strip()
        if not s: return True
        l, r = 0, len(s)-1
        while l <= r:
            if not s[l].isalnum():
                l += 1
            elif not s[r].isalnum():
                r -= 1
            elif s[l] != s[r]:
                return False
            else: 
                l += 1
                r -= 1
        return True
```
#### Notes
- two pointers