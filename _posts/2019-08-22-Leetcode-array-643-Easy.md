---
layout: post
title: '643. Maximum Average Subarray I'
subtitle: ''
date: 2019-08-22
categories: Leetcode
tags: Leetcode Array
---
### [643\. Maximum Average Subarray I](https://leetcode.com/problems/maximum-average-subarray-i/)

Difficulty: **Easy**

Topics: **Array**


Given an array consisting of `n` integers, find the contiguous subarray of given length `k` that has the maximum average value. And you need to output the maximum average value.

**Example 1:**

```
Input: [1,12,-5,-6,50,3], k = 4
Output: 12.75
Explanation: Maximum average is (12-5-6+50)/4 = 51/4 = 12.75
```

**Note:**

1.  1 <= `k` <= `n` <= 30,000.
2.  Elements of the given array will be in the range [-10,000, 10,000].


#### Solution

Language: **Python**

```python
class Solution(object):
    def findMaxAverage(self, nums, k):
        """
        :type nums: List[int]
        :type k: int
        :rtype: float
        """
        ans = cur = sum(nums[:k])
        for i in range(k,len(nums)):
            cur += nums[i]-nums[i-k]
            ans = max(ans,cur)
        return ans*1.0/k
        ans = 0
```
#### Notes 
- sliding window

