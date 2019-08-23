---
layout: post
title: '680. Valid Palindrome II'
subtitle: ''
date: 2019-08-23
categories: Leetcode
tags: Leetcode Strings
---

### [680\. Valid Palindrome II](https://leetcode.com/problems/valid-palindrome-ii/)

Difficulty: **Easy**

Topics: **Strings**


Given a non-empty string `s`, you may delete **at most** one character. Judge whether you can make it a palindrome.

**Example 1:**  

```
Input: "aba"
Output: True
```

**Example 2:**  

```
Input: "abca"
Output: True
Explanation: You could delete the character 'c'.
```

**Note:**  

1.  The string will only contain lowercase characters a-z. The maximum length of the string is 50000.


#### Solution

Language: **Python**

```python
class Solution(object):
    def validPalindrome(self, s):
        """
        :type s: str
        :rtype: bool
        """
        i = 0
        j = len(s)-1
        
        while(j>i):
            if s[i]!=s[j]:
                return (s[i:j]==s[i:j][::-1] or s[i+1:j+1]==s[i+1:j+1][::-1])
            i += 1
            j -= 1
        return True
        
```

#### Notes
- two pointers
- two conditions: `s[l:r]` or `s[l+1:r+1]`