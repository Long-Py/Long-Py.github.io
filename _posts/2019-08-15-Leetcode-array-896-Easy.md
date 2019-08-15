---
layout: post
title: '896. Monotonic Array'
subtitle: ''
date: 2019-08-15
categories: Leetcode
tags: Leetcode Array
---
### [896\. Monotonic Array](https://leetcode.com/problems/monotonic-array/)

Difficulty: **Easy**

Topics: **Array**


An array is _monotonic_ if it is either monotone increasing or monotone decreasing.

An array `A` is monotone increasing if for all `i <= j`, `A[i] <= A[j]`.  An array `A` is monotone decreasing if for all `i <= j`, `A[i] >= A[j]`.

Return `true` if and only if the given array `A` is monotonic.


**Example 1:**

```
Input: [1,2,2,3]
Output: true
```


**Example 2:**

```
Input: [6,5,4,4]
Output: true
```


**Example 3:**

```
Input: [1,3,2]
Output: false
```


**Example 4:**

```
Input: [1,2,4,5]
Output: true
```


**Example 5:**

```
Input: [1,1,1]
Output: true
```

**Note:**

1.  `1 <= A.length <= 50000`
2.  `-100000 <= A[i] <= 100000`


#### Solution

Language: **Python**

```python
class Solution(object):
    def isMonotonic(self, A):
        """
        :type A: List[int]
        :rtype: bool
        """
        
        return all(A[i]<=A[i+1] for i in range(len(A)-1)) or all(A[i]>=A[i+1] for i in range(len(A)-1))
```

#### Notes
- The `all()` function returns True if all items in an iterable are true, otherwise it returns False.
If the iterable object is **empty**, the all() function also returns **True**.