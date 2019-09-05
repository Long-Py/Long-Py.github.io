---
layout: post
title: '453. Minimum Moves to Equal Array Elements'
subtitle: ''
date: 2019-09-05
categories: Leetcode
tags: Leetcode Math Array
---
### [453\. Minimum Moves to Equal Array Elements](https://leetcode.com/problems/minimum-moves-to-equal-array-elements/)

Difficulty: **Easy**

Topics: **Math**

Given a **non-empty** integer array of size _n_, find the minimum number of moves required to make all array elements equal, where a move is incrementing _n_ - 1 elements by 1.

**Example:**

```
Input:
[1,2,3]

Output:
3

Explanation:
Only three moves are needed (remember each move increments two elements):

[1,2,3]  =>  [2,3,3]  =>  [3,4,3]  =>  [4,4,4]
```


#### Solution

Language: **Python**

```python
class Solution(object):
    def minMoves(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        return sum(nums) - min(nums)*len(nums)
```
#### Notes
-  sum + m * (n - 1) = x * n
   
   x = minNum + m
   
   finally, sum - minNum * n = m