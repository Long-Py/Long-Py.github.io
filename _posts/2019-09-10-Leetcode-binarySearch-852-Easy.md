---
layout: post
title: '852. Peak Index in a Mountain Array'
subtitle: ''
date: 2019-09-10
categories: Leetcode
tags: Leetcode BinarySearch
---
### [852\. Peak Index in a Mountain Array](https://leetcode.com/problems/peak-index-in-a-mountain-array/)

Difficulty: **Easy**

Topics: **Binary Search**


Let's call an array `A` a _mountain_ if the following properties hold:

*   `A.length >= 3`
*   There exists some `0 < i < A.length - 1` such that `A[0] < A[1] < ... A[i-1] < A[i] > A[i+1] > ... > A[A.length - 1]`

Given an array that is definitely a mountain, return any `i` such that `A[0] < A[1] < ... A[i-1] < A[i] > A[i+1] > ... > A[A.length - 1]`.

**Example 1:**

```
Input: [0,1,0]
Output: 1
```


**Example 2:**

```
Input: [0,2,1,0]
Output: 1
```


**Note:**

1.  `3 <= A.length <= 10000`
2.  `<font face="monospace" style="display: inline;">0 <= A[i] <= 10^6</font>`
3.  A is a mountain, as defined above.


#### Solution

Language: **Python**

```python
class Solution(object):
    def peakIndexInMountainArray(self, A):
        """
        :type A: List[int]
        :rtype: int
        """
        l, r = 0, len(A)-1
        while l <= r:
            mid = l + (r-l)//2
            if A[mid-1] < A[mid] > A[mid+1]:
                return mid
            elif A[mid-1] < A[mid] < A[mid+1]:
                l = mid + 1
            else:
                r = mid - 1
        return l
```