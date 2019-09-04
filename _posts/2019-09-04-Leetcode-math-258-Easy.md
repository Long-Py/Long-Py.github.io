---
layout: post
title: '258. Add Digits'
subtitle: ''
date: 2019-09-03
categories: Leetcode
tags: Leetcode Math
---
### [258\. Add Digits](https://leetcode.com/problems/add-digits/)

Difficulty: **Easy**

Topics: **Math**


Given a non-negative integer `num`, repeatedly add all its digits until the result has only one digit.

**Example:**

```
Input: 38
Output: 2 
Explanation: The process is like: 3 + 8 = 11, 1 + 1 = 2\. 
             Since 2 has only one digit, return it.
```

**Follow up:**  
Could you do it without any loop/recursion in O(1) runtime?


#### Solution

Language: **Python**

```python
class Solution(object):
    def addDigits(self, num):
        """
        :type num: int
        :rtype: int
        """
        if num == 0: return 0
        return 1 + (num-1)%9
```
#### Notes
- 1 % 9 = 1

    10 % 9 = 1

    100 % 9 = 1

    so N % 9 = a[0] + a[1] + ..a[n]

    means N % 9 = M

    so N = M (% 9)

    as 9 % 9 = 0,so we can make (n - 1) % 9 + 1 to help us solve the problem when n is 9. As N is 9, ( 9 - 1) % 9 + 1 = 9