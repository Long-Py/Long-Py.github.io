---
layout: post
title: '1013. Partition Array Into Three Parts With Equal Sum'
subtitle: ''
date: 2019-08-15
categories: Leetcode
tags: Leetcode Array
---
### [1013\. Partition Array Into Three Parts With Equal Sum](https://leetcode.com/problems/partition-array-into-three-parts-with-equal-sum/)

Difficulty: **Easy**

Topics: **Array**


Given an array `A` of integers, return `true` if and only if we can partition the array into three **non-empty** parts with equal sums.

Formally, we can partition the array if we can find indexes `i+1 < j` with `(A[0] + A[1] + ... + A[i] == A[i+1] + A[i+2] + ... + A[j-1] == A[j] + A[j-1] + ... + A[A.length - 1])`

**Example 1:**

```
Input: [0,2,1,-6,6,-7,9,1,2,0,1]
Output: true
Explanation: 0 + 2 + 1 = -6 + 6 - 7 + 9 + 1 = 2 + 0 + 1
```


**Example 2:**

```
Input: [0,2,1,-6,6,7,9,-1,2,0,1]
Output: false
```


**Example 3:**

```
Input: [3,3,6,5,-2,2,5,1,-9,4]
Output: true
Explanation: 3 + 3 = 6 = 5 - 2 + 2 + 5 + 1 - 9 + 4
```


**Note:**

1.  `3 <= A.length <= 50000`
2.  `-10000 <= A[i] <= 10000`


#### Solution

Language: **Python**

```python
class Solution(object):
    def canThreePartsEqualSum(self, A):
        """
        :type A: List[int]
        :rtype: bool
        """
        s = sum(A)
        if s % 3 != 0:
            return False
        s /= 3
        cur = 0
        count = 0
        for n in A:
            cur += n
            if cur == s:
                count += 1
                cur = 0
        return count == 3
        
        
            
            
```

#### Notes
- **one** pass: calc sum **before** *if* conditional statement
- **two** passes: calc sum from left, and calc sum from right, then return if the sum of the rest elements equals one-thrid of sum(A)