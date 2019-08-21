---
layout: post
title: '53. Maximum Subarray'
subtitle: ''
date: 2019-08-21
categories: Leetcode
tags: Leetcode Array
---
### [53\. Maximum Subarray](https://leetcode.com/problems/maximum-subarray/)

Difficulty: **Easy**

Topics: **Array**


Given an integer array `nums`, find the contiguous subarray (containing at least one number) which has the largest sum and return its sum.

**Example:**

```
Input: [-2,1,-3,4,-1,2,1,-5,4],
Output: 6
Explanation: [4,-1,2,1] has the largest sum = 6.
```

**Follow up:**

If you have figured out the O(_n_) solution, try coding another solution using the divide and conquer approach, which is more subtle.


#### Solution

Language: **Python**

```python
class Solution(object):
    def maxSubArray(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        if not nums: return 0
        for i in range(1,len(nums)):
            if nums[i-1] > 0:
                nums[i] += nums[i-1]
        return max(nums)
```

#### Notes
- [Kadane's algorithm](https://en.wikipedia.org/wiki/Maximum_subarray_problem)
- perform in-place modification of array in order to calculate the sums of contiguous sequences of array elements, wherever those sums are positive. This is ensured by `nums[i-1] > 0` condition. The last positive member of a sequence will contain sum of that particular sequence. If an array contains all negative members the function will simply return the largest number.