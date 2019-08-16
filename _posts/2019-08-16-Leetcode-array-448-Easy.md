---
layout: post
title: '448. Find All Numbers Disappeared in an Array'
subtitle: ''
date: 2019-08-16
categories: Leetcode
tags: Leetcode Array
---
### [448\. Find All Numbers Disappeared in an Array](https://leetcode.com/problems/find-all-numbers-disappeared-in-an-array/)

Difficulty: **Easy**

Topics: **Array**

Given an array of integers where 1 ≤ a[i] ≤ _n_ (_n_ = size of array), some elements appear twice and others appear once.

Find all the elements of [1, _n_] inclusive that do not appear in this array.

Could you do it without extra space and in O(_n_) runtime? You may assume the returned list does not count as extra space.

**Example:**

```
Input:
[4,3,2,7,8,2,3,1]

Output:
[5,6]
```


#### Solution

Language: **Python**

```python
class Solution(object):
    def findDisappearedNumbers(self, nums):
        """
        :type nums: List[int]
        :rtype: List[int]
        """
        for v in nums:
            idx = abs(v)-1
            nums[idx] = -abs(nums[idx])
        return [i+1 for i in range(len(nums)) if nums[i] > 0]
```

#### Notes
- two passes: 1st pass sign negative to index matching the values in list; 2nd pass find the index with positive value, which is the ans.