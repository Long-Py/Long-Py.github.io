---
layout: post
title: '268. Missing Number'
subtitle: ''
date: 2019-08-19
categories: Leetcode
tags: Leetcode Array Math BitManipulation
---
### [268\. Missing Number](https://leetcode.com/problems/missing-number/)

Difficulty: **Easy**

Topics: **Array**


Given an array containing _n_ distinct numbers taken from `0, 1, 2, ..., n`, find the one that is missing from the array.

**Example 1:**

```
Input: [3,0,1]
Output: 2
```

**Example 2:**

```
Input: [9,6,4,2,3,5,7,0,1]
Output: 8
```

**Note**:  
Your algorithm should run in linear runtime complexity. Could you implement it using only constant extra space complexity?


#### Solution

Language: **Python**

```python
class Solution(object):
    def missingNumber(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        ans = len(nums)
        for i, v in enumerate(nums):
            ans ^= i ^ v
        return ans
```

#### Notes
-  XOR is its own inverse: `A ^ A = 0`
-  `A ^ 0 = A`