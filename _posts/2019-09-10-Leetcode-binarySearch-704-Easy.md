---
layout: post
title: '704. Binary Search'
subtitle: ''
date: 2019-09-10
categories: Leetcode
tags: Leetcode BinarySearch
---
### [704\. Binary Search](https://leetcode.com/problems/binary-search/)

Difficulty: **Easy**

Topics: **Binary Search**


Given a **sorted** (in ascending order) integer array `nums` of `n` elements and a `target` value, write a function to search `target` in `nums`. If `target` exists, then return its index, otherwise return `-1`.

**Example 1:**

```
Input: nums = [-1,0,3,5,9,12], target = 9
Output: 4
Explanation: 9 exists in nums and its index is 4

```

**Example 2:**

```
Input: nums = [-1,0,3,5,9,12], target = 2
Output: -1
Explanation: 2 does not exist in nums so return -1
```

**Note:**

1.  You may assume that all elements in `nums` are unique.
2.  `n` will be in the range `[1, 10000]`.
3.  The value of each element in `nums` will be in the range `[-9999, 9999]`.


#### Solution

Language: **Python**

```python
class Solution(object):
    def search(self, nums, target):
        """
        :type nums: List[int]
        :type target: int
        :rtype: int
        """
        l, r = 0, len(nums)-1
        while l <= r:
            mid = l + (r-l)//2
            if nums[mid] == target:
                return mid
            elif nums[mid] < target:
                l = mid+1
            else:
                r =mid-1
        return -1
```