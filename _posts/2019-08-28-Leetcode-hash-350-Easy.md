---
layout: post
title: '350. Intersection of Two Arrays II'
subtitle: ''
date: 2019-08-28
categories: Leetcode
tags: Leetcode Array HashTable TwoPointers Sort
---
### [350\. Intersection of Two Arrays II](https://leetcode.com/problems/intersection-of-two-arrays-ii/)

Difficulty: **Easy**

Topics: **HashTable**


Given two arrays, write a function to compute their intersection.

**Example 1:**

```
Input: nums1 = [1,2,2,1], nums2 = [2,2]
Output: [2,2]
```


**Example 2:**

```
Input: nums1 = [4,9,5], nums2 = [9,4,9,8,4]
Output: [4,9]
```


**Note:**

*   Each element in the result should appear as many times as it shows in both arrays.
*   The result can be in any order.

**Follow up:**

*   What if the given array is already sorted? How would you optimize your algorithm?
*   What if _nums1_'s size is small compared to _nums2_'s size? Which algorithm is better?
*   What if elements of _nums2_ are stored on disk, and the memory is limited such that you cannot load all elements into the memory at once?


#### Solution

Language: **Python**

```python
class Solution(object):
    def intersect(self, nums1, nums2):
        """
        :type nums1: List[int]
        :type nums2: List[int]
        :rtype: List[int]
        """
        if len(nums2) < len(nums1):
            nums1, nums2 = nums2, nums1
        cnt = collections.Counter(nums2)
        ans = []
        for n in nums1:
            if cnt[n] > 0:
                ans.append(n)
                cnt[n] -= 1
        return ans
        
```