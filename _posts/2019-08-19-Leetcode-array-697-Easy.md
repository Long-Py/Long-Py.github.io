---
layout: post
title: '697. Degree of an Array'
subtitle: ''
date: 2019-08-19
categories: Leetcode
tags: Leetcode Array
---
### [697\. Degree of an Array](https://leetcode.com/problems/degree-of-an-array/)

Difficulty: **Easy**

Topics: **Array**


Given a non-empty array of non-negative integers `nums`, the **degree** of this array is defined as the maximum frequency of any one of its elements.

Your task is to find the smallest possible length of a (contiguous) subarray of `nums`, that has the same degree as `nums`.

**Example 1:**  

```
Input: [1, 2, 2, 3, 1]
Output: 2
Explanation: 
The input array has a degree of 2 because both elements 1 and 2 appear twice.
Of the subarrays that have the same degree:
[1, 2, 2, 3, 1], [1, 2, 2, 3], [2, 2, 3, 1], [1, 2, 2], [2, 2, 3], [2, 2]
The shortest length is 2\. So return 2.
```

**Example 2:**  

```
Input: [1,2,2,3,1,4,2]
Output: 6
```

**Note:**

*   `nums.length` will be between 1 and 50,000.*   `nums[i]` will be an integer between 0 and 49,999.

#### Solution

Language: **Python**

```python
class Solution(object):
    def findShortestSubArray(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        first, cnt,degree, ans = {}, {}, 0, float('inf')
        for i, v in enumerate(nums):
            cnt[v] = cnt.get(v, 1) + 1
            if v not in first:
                first[v] = i
            if cnt[v] > degree:
                degree = cnt[v]
                ans = i - first[v] + 1
            elif cnt[v] == degree:
                ans = min(ans,i-first[v]+1)
        return ans
```

#### Notes
- two passes is much easier, but here I use only use one pass: scan the whole list, count elements and put into **cnt dict** and put their first index into **first dict**, when we got a new degree(max cnt) we would calc new result, and when we got a element euqals degree we would compare and set the smaller one as result.