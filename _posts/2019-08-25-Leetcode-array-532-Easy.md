---
layout: post
title: '532. K-diff Pairs in an Array'
subtitle: ''
date: 2019-08-25
categories: Leetcode
tags: Leetcode Array
---

### [532\. K-diff Pairs in an Array](https://leetcode.com/problems/k-diff-pairs-in-an-array/)

Difficulty: **Easy**

Topics: **Array**


Given an array of integers and an integer **k**, you need to find the number of **unique** k-diff pairs in the array. Here a **k-diff** pair is defined as an integer pair (i, j), where **i** and **j** are both numbers in the array and their is **k**.

**Example 1:**  

```
Input: [3, 1, 4, 1, 5], k = 2
Output: 2
Explanation: There are two 2-diff pairs in the array, (1, 3) and (3, 5).Although we have two 1s in the input, we should only return the number of unique pairs.
```

**Example 2:**  

```
Input:[1, 2, 3, 4, 5], k = 1
Output: 4
Explanation: There are four 1-diff pairs in the array, (1, 2), (2, 3), (3, 4) and (4, 5).
```

**Example 3:**  

```
Input: [1, 3, 1, 5, 4], k = 0
Output: 1
Explanation: There is one 0-diff pair in the array, (1, 1).
```

**Note:**  

1.  The pairs (i, j) and (j, i) count as the same pair.
2.  The length of the array won't exceed 10,000.
3.  All the integers in the given input belong to the range: [-1e7, 1e7].


#### Solution

Language: **Python**

```python
class Solution(object):
    def findPairs(self, nums, k):
        """
        :type nums: List[int]
        :type k: int
        :rtype: int
        """
        res = 0
        c = collections.Counter(nums)
        for i in c:
            if k > 0 and i + k in c or k == 0 and c[i] > 1:
                res += 1
        return res
```
#### Notes
- dict: {element:count}
- two conditions: `k > 0` and `k == 0`