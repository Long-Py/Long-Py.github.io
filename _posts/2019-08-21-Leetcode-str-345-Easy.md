---
layout: post
title: '345. Reverse Vowels of a String'
subtitle: ''
date: 2019-08-21
categories: Leetcode
tags: Leetcode Strings TwoPointers
---
### [345\. Reverse Vowels of a String](https://leetcode.com/problems/reverse-vowels-of-a-string/)

Difficulty: **Easy**

Topics: **Strings**

Write a function that takes a string as input and reverse only the vowels of a string.

**Example 1:**

```
Input: "hello"
Output: "holle"
```


**Example 2:**

```
Input: "leetcode"
Output: "leotcede"
```


**Note:**  
The vowels does not include the letter "y".


#### Solution

Language: **Python**

```python
class Solution(object):
    def reverseVowels(self, s):
        """
        :type s: str
        :rtype: str
        """
        vowels = ['a','e','i','o','u','A','E','I','O','U']
        s = list(s)
        l, r = 0, len(s)-1
        while l < r:
            if s[l] in vowels and s[r] in vowels:
                s[l], s[r] = s[r], s[l]
                l += 1
                r -= 1
            elif s[l] not in vowels:
                l += 1
            else:
                r -= 1
        return ''.join(s)
```
#### Notes
- two pointers