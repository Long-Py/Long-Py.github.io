---
layout: post
title: '189. Rotate Array'
subtitle: ''
date: 2019-08-25
categories: Leetcode
tags: Leetcode Array
---

### [189\. Rotate Array](https://leetcode.com/problems/rotate-array/)

Difficulty: **Easy**

Topics: **Array**

Given an array, rotate the array to the right by _k_ steps, where _k_ is non-negative.

**Example 1:**

```
Input: [1,2,3,4,5,6,7] and k = 3
Output: [5,6,7,1,2,3,4]
Explanation:
rotate 1 steps to the right: [7,1,2,3,4,5,6]
rotate 2 steps to the right: [6,7,1,2,3,4,5]
rotate 3 steps to the right: [5,6,7,1,2,3,4]
```

**Example 2:**

```
Input: [-1,-100,3,99] and k = 2
Output: [3,99,-1,-100]
Explanation: 
rotate 1 steps to the right: [99,-1,-100,3]
rotate 2 steps to the right: [3,99,-1,-100]
```

**Note:**

*   Try to come up as many solutions as you can, there are at least 3 different ways to solve this problem.
*   Could you do it in-place with O(1) extra space?


#### Solution

Language: **Python**

```python
class Solution(object):
    def rotate(self, nums, k):
        """
        :type nums: List[int]
        :type k: int
        :rtype: None Do not return anything, modify nums in-place instead.
        """
        n = len(nums)
        k = k % n
        nums[:] = nums[n-k:] + nums[:n-k]
```

#### Notes
- notice: `nums[:]` get a new list