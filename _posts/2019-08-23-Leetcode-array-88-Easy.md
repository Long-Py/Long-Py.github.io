---
layout: post
title: '88. Merge Sorted Array'
subtitle: ''
date: 2019-08-23
categories: Leetcode
tags: Leetcode Array TwoPointers
---
### [88\. Merge Sorted Array](https://leetcode.com/problems/merge-sorted-array/)

Difficulty: **Easy**

Topics: **Array**


Given two sorted integer arrays _nums1_ and _nums2_, merge _nums2_ into _nums1_ as one sorted array.

**Note:**

*   The number of elements initialized in _nums1_ and _nums2_ are _m_ and _n_ respectively.
*   You may assume that _nums1_ has enough space (size that is greater or equal to _m_ + _n_) to hold additional elements from _nums2_.

**Example:**

```
Input:
nums1 = [1,2,3,0,0,0], m = 3
nums2 = [2,5,6],       n = 3

Output: [1,2,2,3,5,6]
```


#### Solution

Language: **Python**

```python
class Solution(object):
    def merge(self, nums1, m, nums2, n):
        """
        :type nums1: List[int]
        :type m: int
        :type nums2: List[int]
        :type n: int
        :rtype: None Do not return anything, modify nums1 in-place instead.
        """
        l = m+n-1
        l1 = m-1
        l2 = n-1
        while l1 >= 0 and l2 >= 0:
            if nums1[l1] >= nums2[l2]:
                nums1[l] = nums1[l1]
                l1 -= 1
            else:
                nums1[l] = nums2[l2]
                l2 -= 1
            l -= 1
        
        if l2 >= 0:
            nums1[:l2+1] = nums2[:l2+1] 
```
#### Notes
- scan from back to front
- `if not l1`, check if there is any l2.