---
layout: post
title: '976. Largest Perimeter Triangle'
subtitle: ''
date: 2019-09-03
categories: Leetcode
tags: Leetcode Math Array Sort
---
### [976\. Largest Perimeter Triangle](https://leetcode.com/problems/largest-perimeter-triangle/)

Difficulty: **Easy**

Topics: **Math**


Given an array `A` of positive lengths, return the largest perimeter of a triangle with **non-zero area**, formed from 3 of these lengths.

If it is impossible to form any triangle of non-zero area, return `0`.


**Example 1:**

```
Input: [2,1,2]
Output: 5
```


**Example 2:**

```
Input: [1,2,1]
Output: 0
```


**Example 3:**

```
Input: [3,2,3,4]
Output: 10
```


**Example 4:**

```
Input: [3,6,2,3]
Output: 8
```

**Note:**

1.  `3 <= A.length <= 10000`
2.  `1 <= A[i] <= 10^6`


#### Solution

Language: **Python**

```python
class Solution(object):
    def largestPerimeter(self, A):
        """
        :type A: List[int]
        :rtype: int
        """
        A.sort()
        for i in xrange(len(A) - 3, -1, -1):
            if A[i] + A[i+1] > A[i+2]:
                return A[i] + A[i+1] + A[i+2]
        return 0        
```
#### Notes
- time complexity: O(nlogn)