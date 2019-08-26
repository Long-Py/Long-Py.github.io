---
layout: post
title: '581. Shortest Unsorted Continuous Subarray'
subtitle: ''
date: 2019-08-25
categories: Leetcode
tags: Leetcode Array
---
### [581\. Shortest Unsorted Continuous Subarray](https://leetcode.com/problems/shortest-unsorted-continuous-subarray/)

Difficulty: **Easy**

Topics: **Array**


Given an integer array, you need to find one **continuous subarray** that if you only sort this subarray in ascending order, then the whole array will be sorted in ascending order, too.

You need to find the **shortest** such subarray and output its length.

**Example 1:**  

```
Input: [2, 6, 4, 8, 10, 9, 15]
Output: 5
Explanation: You need to sort [6, 4, 8, 10, 9] in ascending order to make the whole array sorted in ascending order.
```

**Note:**  

1.  Then length of the input array is in range [1, 10,000].
2.  The input array may contain duplicates, so ascending order here means **<=**.


#### Solution

Language: **Python**

```python
class Solution(object):
    def findUnsortedSubarray(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        if len(nums) < 2: return 0
        
        l, r = 0, len(nums) - 1
        
        while l < len(nums) - 1 and nums[l] <= nums[l + 1]:
            l += 1
        
        while r > 0 and nums[r] >= nums[r -1]:
            r -= 1
            
        if l > r:
            return 0
            
        temp = nums[l:r+1]
        tempMin = min(temp)
        tempMax = max(temp)
        
        while l > 0 and tempMin < nums[l-1]:
            l -= 1
        
        while r < len(nums) - 1 and tempMax > nums[r+1]:
            r += 1
            
        return r - l + 1        
        while l < len(nums) - 1 and nums[l] <= nums[l + 1]:
```

#### Notes
- two passes: 1st finds the segments that are already sorted; 2nd finds the elements between min and max.