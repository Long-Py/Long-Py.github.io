---
layout: post
title: '198. House Robber'
subtitle: ''
date: 2019-09-12
categories: Leetcode
tags: Leetcode DP
---
### [198\. House Robber](https://leetcode.com/problems/house-robber/)

Difficulty: **Easy**

Topics: **DP**

You are a professional robber planning to rob houses along a street. Each house has a certain amount of money stashed, the only constraint stopping you from robbing each of them is that adjacent houses have security system connected and **it will automatically contact the police if two adjacent houses were broken into on the same night**.

Given a list of non-negative integers representing the amount of money of each house, determine the maximum amount of money you can rob tonight **without alerting the police**.

**Example 1:**

```
Input: [1,2,3,1]
Output: 4
Explanation: Rob house 1 (money = 1) and then rob house 3 (money = 3).
             Total amount you can rob = 1 + 3 = 4.
```

**Example 2:**

```
Input: [2,7,9,3,1]
Output: 12
Explanation: Rob house 1 (money = 2), rob house 3 (money = 9) and rob house 5 (money = 1).
             Total amount you can rob = 2 + 9 + 1 = 12.
```


#### Solution

Language: **Python**

```python
class Solution(object):
    def rob(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        if not nums: return 0
        if len(nums) < 3: return max(nums)
        for i in range(2,len(nums)):
            nums[i-1], nums[i] = max(nums[i-1],nums[i-2]), max(nums[i-1], nums[i]+nums[i-2])
        return nums[-1]
```