---
layout: post
title: '1089. Duplicate Zeros'
subtitle: ''
date: 2019-08-14
categories: Leetcode
tags: Leetcode Array
---
### [1089\. Duplicate Zeros](https://leetcode.com/problems/duplicate-zeros/)

Difficulty: **Easy**

Topics: **Array**


Given a fixed length array `arr` of integers, duplicate each occurrence of zero, shifting the remaining elements to the right.

Note that elements beyond the length of the original array are not written.

Do the above modifications to the input array **in place**, do not return anything from your function.

**Example 1:**

```
Input: [1,0,2,3,0,4,5,0]
Output: null
Explanation: After calling your function, the input array is modified to: [1,0,0,2,3,0,0,4]
```

**Example 2:**

```
Input: [1,2,3]
Output: null
Explanation: After calling your function, the input array is modified to: [1,2,3]
```

**Note:**

1.  `1 <= arr.length <= 10000`
2.  `0 <= arr[i] <= 9`


#### Solution

Language: **Python**

```python
class Solution(object):
    def duplicateZeros(self, arr):
        """
        :type arr: List[int]
        :rtype: None Do not return anything, modify arr in-place instead.
        """
        cnt = arr.count(0)
        l = len(arr)
        for i in range(l-1, -1, -1):
            # shift value to correct postion
            if i+cnt < l:   #only consider index from len(arr) to 0
                arr[i+cnt] = arr[i]
            # if val == 0, duplicate one more 0
            if arr[i] == 0:
                cnt -= 1
                if i+cnt < l:
                    arr[i+cnt] = 0
        return arr
```

#### Notes
- **Two passes.** The 1st pass get the count of zero, the 2nd pass track from **back** of arr and shift value to correct position.