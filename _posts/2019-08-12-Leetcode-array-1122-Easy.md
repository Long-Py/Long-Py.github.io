---
layout: post
title: '1122. Relative Sort Array'
subtitle: ''
date: 2019-08-12
categories: Leetcode
tags: Leetcode Array Sort
---
### [1122\. Relative Sort Array](https://leetcode.com/problems/relative-sort-array/)

Difficulty: **Easy**

Topics: **Array**


Given two arrays `arr1` and `arr2`, the elements of `arr2` are distinct, and all elements in `arr2` are also in `arr1`.

Sort the elements of `arr1` such that the relative ordering of items in `arr1` are the same as in `arr2`.  Elements that don't appear in `arr2` should be placed at the end of `arr1` in **ascending** order.

**Example 1:**

```
Input: arr1 = [2,3,1,3,2,4,6,7,9,2,19], arr2 = [2,1,4,3,9,6]
Output: [2,2,2,1,4,3,3,9,6,7,19]
```

**Constraints:**

*   `arr1.length, arr2.length <= 1000`
*   `0 <= arr1[i], arr2[i] <= 1000`
*   Each `arr2[i]` is distinct.
*   Each `arr2[i]` is in `arr1`.


#### Solution

Language: **Python**

```python
class Solution(object):
    def relativeSortArray(self, arr1, arr2):
        """
        :type arr1: List[int]
        :type arr2: List[int]
        :rtype: List[int]
        """
        d = {v:i for i,v in enumerate(arr2)}
        
        return sorted(arr1,key=lambda i:d.get(i,len(arr2)+i))
```

#### Notes
- sort by arr2 index; if element not in arr2, set index to **length** of arr2 plus **value** of this element.