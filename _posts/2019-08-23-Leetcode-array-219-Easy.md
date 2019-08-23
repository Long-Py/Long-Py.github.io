---
layout: post
title: '219. Contains Duplicate II'
subtitle: ''
date: 2019-08-23
categories: Leetcode
tags: Leetcode Array
---
### [219\. Contains Duplicate II](https://leetcode.com/problems/contains-duplicate-ii/)

Difficulty: **Easy**

Topics: **Array**


Given an array of integers and an integer _k_, find out whether there are two distinct indices _i_ and _j_ in the array such that **nums[i] = nums[j]** and the **absolute** difference between _i_ and _j_ is at most _k_.


**Example 1:**

```
Input: nums = [1,2,3,1], k = 3
Output: true
```


**Example 2:**

```
Input: nums = [1,0,1,1], k = 1
Output: true
```


**Example 3:**

```
Input: nums = [1,2,3,1,2,3], k = 2
Output: false
```


#### Solution

Language: **Python**

```python
class Solution(object):
    def containsNearbyDuplicate(self, nums, k):
        """
        :type nums: List[int]
        :type k: int
        :rtype: bool
        """
        idx = {}
        for i, v in enumerate(nums):
            if v in idx and i-idx[v] <= k:
                return True
            idx[v] = i
        return False
```

#### Notes 
- use dict to keep track of previous index