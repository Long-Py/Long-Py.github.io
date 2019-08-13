---
layout: post
title: '867. Transpose Matrix'
subtitle: ''
date: 2019-08-13
categories: Leetcode
tags: Leetcode Array
---
### [867\. Transpose Matrix](https://leetcode.com/problems/transpose-matrix/)

Difficulty: **Easy**

Topics: **Array**


Given a matrix `A`, return the transpose of `A`.

The transpose of a matrix is the matrix flipped over it's main diagonal, switching the row and column indices of the matrix.


**Example 1:**

```
Input: [[1,2,3],[4,5,6],[7,8,9]]
Output: [[1,4,7],[2,5,8],[3,6,9]]
```


**Example 2:**

```
Input: [[1,2,3],[4,5,6]]
Output: [[1,4],[2,5],[3,6]]
```

<span style="display: inline;">**Note:**</span>

1.  `<span style="display: inline;">1 <= A.length <= 1000</span>`
2.  `<span style="display: inline;">1 <= A[0].length <= 1000</span>`


#### Solution

Language: **Python**

```python
class Solution(object):
    def transpose(self, A):
        """
        :type A: List[List[int]]
        :rtype: List[List[int]]
        """
        return list(zip(*A))
```

#### Notes
- `*A` : **asterisk** here is used for **unpacking** the containers(usually list, tuple, dict, etc.) and return a **zip** datatype.
- You can also use a nest *for loop* to swap value. 
  
  `A[r][c] = A[c][r]`