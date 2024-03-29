---
layout: post
title: '66. Plus One'
subtitle: ''
date: 2019-08-21
categories: Leetcode
tags: Leetcode Array
---

### [66\. Plus One](https://leetcode.com/problems/plus-one/)

Difficulty: **Easy**

Topics: **Array**

Given a **non-empty** array of digits representing a non-negative integer, plus one to the integer.

The digits are stored such that the most significant digit is at the head of the list, and each element in the array contain a single digit.

You may assume the integer does not contain any leading zero, except the number 0 itself.

**Example 1:**

```
Input: [1,2,3]
Output: [1,2,4]
Explanation: The array represents the integer 123.
```

**Example 2:**

```
Input: [4,3,2,1]
Output: [4,3,2,2]
Explanation: The array represents the integer 4321.
```


#### Solution

Language: **Python**

```python
class Solution(object):
    def plusOne(self, digits):
        """
        :type digits: List[int]
        :rtype: List[int]
        """
        carry = 1
        for i in range(len(digits)-1, -1, -1):
            s = digits[i] + carry
            digits[i] = s%10
            carry = s//10
        
        if carry:
            return [1] + digits
        return digits
            
```

#### Notes
- variable *carry* carries 1.