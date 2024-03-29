---
layout: post
title: '566. Reshape the Matrix'
subtitle: ''
date: 2019-08-13
categories: Leetcode
tags: Leetcode Array
---
### [566\. Reshape the Matrix](https://leetcode.com/problems/reshape-the-matrix/)

Difficulty: **Easy**

Topics: **Array**

In MATLAB, there is a very useful function called 'reshape', which can reshape a matrix into a new one with different size but keep its original data.

You're given a matrix represented by a two-dimensional array, and two **positive** integers **r** and **c** representing the **row** number and **column** number of the wanted reshaped matrix, respectively.

The reshaped matrix need to be filled with all the elements of the original matrix in the same **row-traversing** order as they were.

If the 'reshape' operation with given parameters is possible and legal, output the new reshaped matrix; Otherwise, output the original matrix.

**Example 1:**  

```
Input: 
nums = 
[[1,2],
 [3,4]]
r = 1, c = 4
Output: 
[[1,2,3,4]]
Explanation:The row-traversing of nums is [1,2,3,4]. The new reshaped matrix is a 1 * 4 matrix, fill it row by row by using the previous list.
```

**Example 2:**  

```
Input: 
nums = 
[[1,2],
 [3,4]]
r = 2, c = 4
Output: 
[[1,2],
 [3,4]]
Explanation:There is no way to reshape a 2 * 2 matrix to a 2 * 4 matrix. So output the original matrix.
```

**Note:**  

1.  The height and width of the given matrix is in range [1, 100].
2.  The given r and c are all positive.


#### Solution

Language: **Python**

```python
class Solution(object):
    def matrixReshape(self, nums, r, c):
        """
        :type nums: List[List[int]]
        :type r: int
        :type c: int
        :rtype: List[List[int]]
        """
        row = len(nums)
        col = len(nums[0])
        if row*col != r*c: return nums
        flat = [nums[i][j] for i in range(row) for j in range(col)]
        idx = 0
        res = []
        for i in range(r):
            tmp = []
            for j in range(c):
                tmp.append(flat[idx])
                idx += 1
            res.append(tmp)
        return res
        
        
```

#### Notes
1. flat matrix to list
2. append value row by row
3. time complexity: O(m*n)