---
layout: post
title: '941. Valid Mountain Array'
subtitle: ''
date: 2019-08-23
categories: Leetcode
tags: Leetcode Array
---

### [941\. Valid Mountain Array](https://leetcode.com/problems/valid-mountain-array/)

Difficulty: **Easy**

Topics: **Array**

Given an array `A` of integers, return `true` if and only if it is a _valid mountain array_.

Recall that A is a mountain array if and only if:

*   `A.length >= 3`
*   There exists some `i` with `0 < i < A.length - 1` such that:
    *   `A[0] < A[1] < ... A[i-1] < A[i]`
    *   `A[i] > A[i+1] > ... > A[A.length - 1]`

**Example 1:**

```
Input: [2,1]
Output: false
```


**Example 2:**

```
Input: [3,5,5]
Output: false
```


**Example 3:**

```
Input: [0,3,2,1]
Output: true
```


**Note:**

1.  `0 <= A.length <= 10000`
2.  `0 <= A[i] <= 10000 `


#### Solution

Language: **Python**

```python
class Solution(object):
    def validMountainArray(self, A):
        """
        :type A: List[int]
        :rtype: bool
        """
        if len(A) < 3: return False
        i = 0
        # up
        while i < len(A)-1 and A[i] < A[i+1]:
            i += 1
        
        #  Monotonically increasing or decreasing
        if i == 0 or i == len(A)-1:
            return False
        
        # down
        while i < len(A)-1 and A[i] > A[i+1]:
            i += 1
        
        return i == len(A)-1
```

#### Notes
- one pass: going up and then down 
- notice: edge cases: peak at the beginning or end of list
- two passes: 1st gets the index of peak value, 2nd check Monotonically increasing or decreasing