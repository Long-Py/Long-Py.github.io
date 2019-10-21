---
layout: post
title: '1030. Matrix Cells in Distance Order'
subtitle: ''
date: 2019-10-21
categories: Leetcode
tags: Leetcode Sort Array
---
### [1030\. Matrix Cells in Distance Order](https://leetcode.com/problems/matrix-cells-in-distance-order/)

Difficulty: **Easy**

Topics: **Sort**

We are given a matrix with `R` rows and `C` columns has cells with integer coordinates `(r, c)`, where `0 <= r < R` and `0 <= c < C`.

Additionally, we are given a cell in that matrix with coordinates `(r0, c0)`.

Return the coordinates of all cells in the matrix, sorted by their distance from `(r0, c0)` from smallest distance to largest distance.  Here, the distance between two cells `(r1, c1)` and `(r2, c2)` is the Manhattan distance, `|r1 - r2| + |c1 - c2|`.  (You may return the answer in any order that satisfies this condition.)


**Example 1:**

```
Input: R = 1, C = 2, r0 = 0, c0 = 0
Output: [[0,0],[0,1]]
Explanation: The distances from (r0, c0) to other cells are: [0,1]
```


**Example 2:**

```
Input: R = 2, C = 2, r0 = 0, c0 = 1
Output: [[0,1],[0,0],[1,1],[1,0]]
Explanation: The distances from (r0, c0) to other cells are: [0,1,1,2]
The answer [[0,1],[1,1],[0,0],[1,0]] would also be accepted as correct.
```


**Example 3:**

```
Input: R = 2, C = 3, r0 = 1, c0 = 2
Output: [[1,2],[0,2],[1,1],[0,1],[1,0],[0,0]]
Explanation: The distances from (r0, c0) to other cells are: [0,1,1,2,2,3]
There are other answers that would also be accepted as correct, such as [[1,2],[1,1],[0,2],[1,0],[0,1],[0,0]].
```

**<span style="display: inline;">Note:</span>**

1.  `1 <= R <= 100`
2.  `1 <= C <= 100`
3.  `0 <= r0 < R`
4.  `0 <= c0 < C`


#### Solution

Language: **Python**

```python
class Solution(object):
    def allCellsDistOrder(self, R, C, r0, c0):
        """
        :type R: int
        :type C: int
        :type r0: int
        :type c0: int
        :rtype: List[List[int]]
        """
        matrix = [[i,j] for i in range(R) for j in range(C)]
        return sorted(matrix,key=lambda (x,y):abs(x-r0)+abs(y-c0))
        
```

#### Notes

- `lambda` with 2 arguments

    lambda `(x,y)`: abs(x-r0) + abs(y-c0)