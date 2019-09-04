---
layout: post
title: '892. Surface Area of 3D Shapes'
subtitle: ''
date: 2019-09-03
categories: Leetcode
tags: Leetcode Math Array
---
### [892\. Surface Area of 3D Shapes](https://leetcode.com/problems/surface-area-of-3d-shapes/)

Difficulty: **Easy**

Topics: **Math**

On a `N * N` grid, we place some `1 * 1 * 1 `cubes.

Each value `v = grid[i][j]` represents a tower of `v` cubes placed on top of grid cell `(i, j)`.

Return the total surface area of the resulting shapes.


**Example 1:**

```
Input: [[2]]
Output: 10
```


**Example 2:**

```
Input: [[1,2],[3,4]]
Output: 34
```


**Example 3:**

```
Input: [[1,0],[0,2]]
Output: 16
```


**Example 4:**

```
Input: [[1,1,1],[1,0,1],[1,1,1]]
Output: 32
```


**Example 5:**

```
Input: [[2,2,2],[2,1,2],[2,2,2]]
Output: 46
```

**Note:**

*   `1 <= N <= 50`
*   `0 <= grid[i][j] <= 50`


#### Solution

Language: **Python**

```python
class Solution(object):
    def surfaceArea(self, grid):
        """
        :type grid: List[List[int]]
        :rtype: int
        """
        ans = 0
        for i in range(len(grid)):
            for j in range(len(grid[0])):
                if grid[i][j]:
                    ans += grid[i][j]*6
                    ans -= (grid[i][j]-1)*2
                    if i < len(grid)-1:
                        ans -= 2 * min(grid[i][j], grid[i+1][j])
                    if j < len(grid[0]) - 1:
                        ans -= 2 * min(grid[i][j], grid[i][j+1])
        return ans
```
#### Notes
- time complexity: O(n^2)