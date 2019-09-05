---
layout: post
title: '202. Happy Number'
subtitle: ''
date: 2019-08-28
categories: Leetcode
tags: Leetcode Array HashTable Math
---
### [202\. Happy Number](https://leetcode.com/problems/happy-number/)

Difficulty: **Easy**

Topics: **HashTable**


Write an algorithm to determine if a number is "happy".

A happy number is a number defined by the following process: Starting with any positive integer, replace the number by the sum of the squares of its digits, and repeat the process until the number equals 1 (where it will stay), or it loops endlessly in a cycle which does not include 1\. Those numbers for which this process ends in 1 are happy numbers.

**Example: **

```
Input: 19
Output: true
Explanation: 
12 + 92 = 82
82 + 22 = 68
62 + 82 = 100
12 + 02 + 02 = 1
```


#### Solution

Language: **Python**

```python
class Solution(object):
    def isHappy(self, n):
        """
        :type n: int
        :rtype: bool
        """
        st = set()
        while n != 1:
            s = 0
            while n > 0:
                s += (n%10)**2
                n /= 10
            if s not in st:
                st.add(s)
                n = s
            else:
                return False
        return True
```
