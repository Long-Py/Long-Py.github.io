---
layout: post
title: '303. Range Sum Query - Immutable'
subtitle: ''
date: 2019-09-12
categories: Leetcode
tags: Leetcode DP
---
### [303\. Range Sum Query - Immutable](https://leetcode.com/problems/range-sum-query-immutable/)

Difficulty: **Easy**

Topics: **DP**

Given an integer array _nums_, find the sum of the elements between indices _i_ and _j_ (_i_ ≤ _j_), inclusive.

**Example:**  

```
Given nums = [-2, 0, 3, -5, 2, -1]

sumRange(0, 2) -> 1
sumRange(2, 5) -> -1
sumRange(0, 5) -> -3
```

**Note:**  

1.  You may assume that the array does not change.
2.  There are many calls to _sumRange_ function.


#### Solution

Language: **Python**

```python
class NumArray(object):
​
    def __init__(self, nums):
        """
        :type nums: List[int]
        """
        self.accu = [0]
        for num in nums: 
            self.accu += [self.accu[-1] + num]
​
    def sumRange(self, i, j):
        """
        :type i: int
        :type j: int
        :rtype: int
        """
        return self.accu[j+1]-self.accu[i]
​
​
# Your NumArray object will be instantiated and called as such:
# obj = NumArray(nums)
# param_1 = obj.sumRange(i,j)
```