---
layout: post
title: '977. Squares of a Sorted Array'
subtitle: ''
date: 2019-08-09
categories: Leetcode
tags: Leetcode Array
---
### [977\. Squares of a Sorted ArrayCopy for MarkdownCopy for Markdown](https://leetcode.com/problems/squares-of-a-sorted-array/)

Difficulty: **Easy**

Topics: **Array**


Given an array of integers `A` sorted in non-decreasing order, return an array of the squares of each number, also in sorted non-decreasing order.


**Example 1:**

```
Input: [-4,-1,0,3,10]
Output: [0,1,9,16,100]
```


**Example 2:**

```
Input: [-7,-3,2,3,11]
Output: [4,9,9,49,121]
```

**<span style="display: inline;">Note:</span>**

1.  `<span style="display: inline;">1 <= A.length <= 10000</span>`
2.  `-10000 <= A[i] <= 10000`
3.  `A` is sorted in non-decreasing order.


#### Solution

Language: **Python**

```python
class Solution(object):
    def sortedSquares(self, A):
        """
        :type A: List[int]
        :rtype: List[int]
        """
        return sorted(map(lambda x:x**2,A), key = lambda x:x**2)
```

#### Notes
- `map()` function returns a list of the results after applying the given function to each item of a given **iterable** (list, tuple etc.)