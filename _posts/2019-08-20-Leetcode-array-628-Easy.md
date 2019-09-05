---
layout: post
title: '628. Maximum Product of Three Numbers'
subtitle: ''
date: 2019-08-20
categories: Leetcode
tags: Leetcode Array Math
---
### [628\. Maximum Product of Three Numbers](https://leetcode.com/problems/maximum-product-of-three-numbers/)

Difficulty: **Easy**

Topics: **Array**


Given an integer array, find three numbers whose product is maximum and output the maximum product.

**Example 1:**

```
Input: [1,2,3]
Output: 6
```

**Example 2:**

```
Input: [1,2,3,4]
Output: 24
```

**Note:**

1.  The length of the given array will be in range [3,10<sup>4</sup>] and all elements are in the range [-1000, 1000].
2.  Multiplication of any three numbers in the input won't exceed the range of 32-bit signed integer.


#### Solution

Language: **Python**

```python
class Solution(object):
    def maximumProduct(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        nums = sorted(nums)
        return max(nums[0]*nums[1]*nums[-1], nums[-1]*nums[-2]*nums[-3])
```

#### Notes
- only two conditions: nums[0] and nums[1] are negative, and nums[0] and nums[1] are positive.
- time complexity: O(nlogn)