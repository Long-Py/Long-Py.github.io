---
layout: post
title: '1. Two Sum'
subtitle: ''
date: 2019-08-21
categories: Leetcode
tags: Leetcode Array HashTable
---
### [1\. Two Sum](https://leetcode.com/problems/two-sum/)

Difficulty: **Easy**

Topics: **Array**

Given an array of integers, return **indices** of the two numbers such that they add up to a specific target.

You may assume that each input would have **_exactly_** one solution, and you may not use the _same_ element twice.

**Example:**

```
Given nums = [2, 7, 11, 15], target = 9,

Because nums[0] + nums[1] = 2 + 7 = 9,
return [0, 1].
```


#### Solution

Language: **Python**

```python
class Solution(object):
    def twoSum(self, nums, target):
        """
        :type nums: List[int]
        :type target: int
        :rtype: List[int]
        """
        d = {}
        for i,n in enumerate(nums):
            if target-n in d:
                return [d[target-n], i]
            d[n] = i
        
```

#### Notes
- put value, index pair into dict, if target-n in dict, return list of index