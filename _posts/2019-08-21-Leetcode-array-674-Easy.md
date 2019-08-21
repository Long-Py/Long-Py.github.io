---
layout: post
title: '674. Longest Continuous Increasing Subsequence'
subtitle: ''
date: 2019-08-21
categories: Leetcode
tags: Leetcode Array
---
### [674\. Longest Continuous Increasing Subsequence](https://leetcode.com/problems/longest-continuous-increasing-subsequence/)

Difficulty: **Easy**

Topics: **Array**


Given an unsorted array of integers, find the length of longest `continuous` increasing subsequence (subarray).

**Example 1:**  

```
Input: [1,3,5,4,7]
Output: 3
Explanation: The longest continuous increasing subsequence is [1,3,5], its length is 3\. 
Even though [1,3,5,7] is also an increasing subsequence, it's not a continuous one where 5 and 7 are separated by 4\. 
```

**Example 2:**  

```
Input: [2,2,2,2,2]
Output: 1
Explanation: The longest continuous increasing subsequence is [2], its length is 1\. 
```

**Note:** Length of the array will not exceed 10,000.


#### Solution

Language: **Python**

```python
class Solution(object):
    def findLengthOfLCIS(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        if not nums: return 0
        cur,ans = 1, 1
        for i in range(len(nums)-1):
            if nums[i+1] > nums[i]:
                cur += 1
                ans = max(ans,cur)
            else:
                ans = max(ans,cur)
                cur = 1
        return ans
```
