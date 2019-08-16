---
layout: post
title: '283. Move Zeroes'
subtitle: ''
date: 2019-08-15
categories: Leetcode
tags: Leetcode Array
---
### [283\. Move Zeroes](https://leetcode.com/problems/move-zeroes/)

Difficulty: **Easy**

Topics: **Array**


Given an array `nums`, write a function to move all `0`'s to the end of it while maintaining the relative order of the non-zero elements.

**Example:**

```
Input: [0,1,0,3,12]
Output: [1,3,12,0,0]```

**Note**:

1.  You must do this **in-place** without making a copy of the array.
2.  Minimize the total number of operations.


#### Solution

Language: **Python**

```python
class Solution(object):
    def moveZeroes(self, nums):
        """
        :type nums: List[int]
        :rtype: None Do not return anything, modify nums in-place instead.
        """
        zero = 0
        for i in xrange(len(nums)):
            if nums[i] != 0:
                nums[i], nums[zero] = nums[zero], nums[i]
                zero += 1
                
```
#### Notes
- track zero index from 0, scan list when element is not 0 swap value then increase zero index by 1.