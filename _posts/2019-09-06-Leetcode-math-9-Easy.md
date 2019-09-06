---
layout: post
title: '9. Palindrome Number'
subtitle: ''
date: 2019-09-06
categories: Leetcode
tags: Leetcode Math
---
### [9\. Palindrome Number](https://leetcode.com/problems/palindrome-number/)

Difficulty: **Easy**

Topics: **Math**


Determine whether an integer is a palindrome. An integer is a palindrome when it reads the same backward as forward.

**Example 1:**

```
Input: 121
Output: true
```

**Example 2:**

```
Input: -121
Output: false
Explanation: From left to right, it reads -121\. From right to left, it becomes 121-. Therefore it is not a palindrome.
```

**Example 3:**

```
Input: 10
Output: false
Explanation: Reads 01 from right to left. Therefore it is not a palindrome.
```

**Follow up:**

Coud you solve it without converting the integer to a string?


#### Solution

Language: **Python**

```python
class Solution(object):
    def isPalindrome(self, x):
        """
        :type x: int
        :rtype: bool
        """
        if x < 0: return False
        y = 0
        tmp = x 
        while tmp != 0:
            y *= 10
            y += tmp%10
            tmp //= 10
        
        return y == x
```
#### Notes
- cant use x directly.