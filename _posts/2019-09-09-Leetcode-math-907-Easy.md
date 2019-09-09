---
layout: post
title: '507. Perfect Number'
subtitle: ''
date: 2019-09-09
categories: Leetcode
tags: Leetcode Math
---
### [507\. Perfect Number](https://leetcode.com/problems/perfect-number/)

Difficulty: **Easy**

Topics: **Math**


We define the Perfect Number is a **positive** integer that is equal to the sum of all its **positive** divisors except itself.

Now, given an **integer** n, write a function that returns true when it is a perfect number and false when it is not.

**Example:**  

```
Input: 28
Output: True
Explanation: 28 = 1 + 2 + 4 + 7 + 14
```

**Note:** The input number **n** will not exceed 100,000,000\. (1e8)


#### Solution

Language: **Python**

```python
class Solution(object):
    def checkPerfectNumber(self, num):
        """
        :type num: int
        :rtype: bool
        """
        if num <= 1: return False
        ans = 1
        for i in range(2,int(math.sqrt(num))+1):
            if num%i == 0:
                ans += i + num//i
        
        return ans == num
```
#### Notes
- time complexity: O(logn)