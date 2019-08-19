---
layout: post
title: '167. Two Sum II - Input array is sorted'
subtitle: ''
date: 2019-08-19
categories: Leetcode
tags: Leetcode Array
---

### [167\. Two Sum II - Input array is sorted](https://leetcode.com/problems/two-sum-ii-input-array-is-sorted/)

Difficulty: **Easy**

Topics: **Array**

Given an array of integers that is already **_sorted in ascending order_**, find two numbers such that they add up to a specific target number.

The function twoSum should return indices of the two numbers such that they add up to the target, where index1 must be less than index2.

**Note:**

*   Your returned answers (both index1 and index2) are not zero-based.
*   You may assume that each input would have _exactly_ one solution and you may not use the _same_ element twice.

**Example:**

```
Input: numbers = [2,7,11,15], target = 9
Output: [1,2]
Explanation: The sum of 2 and 7 is 9\. Therefore index1 = 1, index2 = 2.
```


#### Solution

Language: **Python**

```python
class Solution(object):
    def twoSum(self, numbers, target):
        """
        :type numbers: List[int]
        :type target: int
        :rtype: List[int]
        """
        l ,r = 0, len(numbers)-1
        while l < r:
            if numbers[l]+numbers[r] == target:
                return [l+1,r+1]
            elif numbers[l]+numbers[r] < target:
                l += 1
            else:
                r -= 1
```

#### Notes
- two pointers
