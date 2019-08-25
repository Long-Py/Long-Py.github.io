---
layout: post
title: '58. Length of Last Word'
subtitle: ''
date: 2019-08-24
categories: Leetcode
tags: Leetcode Strings
---
### [58\. Length of Last Word](https://leetcode.com/problems/length-of-last-word/)

Difficulty: **Easy**

Topics: **Strings**


Given a string _s_ consists of upper/lower-case alphabets and empty space characters `' '`, return the length of last word in the string.

If the last word does not exist, return 0.

**Note:** A word is defined as a character sequence consists of non-space characters only.

**Example:**

```
Input: "Hello World"
Output: 5
```


#### Solution

Language: **Python**

```python
class Solution(object):
    def lengthOfLastWord(self, s):
        """
        :type s: str
        :rtype: int
        """
        cnt = 0
        tail = len(s)-1
        while tail>=0 and s[tail] == ' ':
            tail -= 1
        
        while tail >= 0 and s[tail] != ' ':
            cnt += 1
            tail -= 1
        
        return cnt
​
```
#### Notes
- two passes: 1st get the first non space char from back end; 2nd get the length of non space chars