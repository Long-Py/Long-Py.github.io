---
layout: post
title: '463. Island Perimeter'
subtitle: ''
date: 2019-08-26
categories: Leetcode
tags: Leetcode Array
---

### [463\. Island Perimeter](https://leetcode.com/problems/island-perimeter/)

Difficulty: **Easy**

Topics: **Array**


You are given a map in form of a two-dimensional integer grid where 1 represents land and 0 represents water.

Grid cells are connected horizontally/vertically (not diagonally). The grid is completely surrounded by water, and there is exactly one island (i.e., one or more connected land cells).

The island doesn't have "lakes" (water inside that isn't connected to the water around the island). One cell is a square with side length 1\. The grid is rectangular, width and height don't exceed 100\. Determine the perimeter of the island.

**Example:**

```
Input:
[[0,1,0,0],
 [1,1,1,0],
 [0,1,0,0],
 [1,1,0,0]]

Output: 16

Explanation: The perimeter is the 16 yellow stripes in the image below:

```


#### Solution

Language: **Python**

```python
class Solution(object):
    def islandPerimeter(self, grid):
        """
        :type grid: List[List[int]]
        :rtype: int
        """
        row, col = len(grid), len(grid[0])
        ans = 0
        for x in range(row):
            for y in range(col):
                if grid[x][y] == 1:
                    ans += 4
                    if x < row - 1 and grid[x+1][y] == 1:
                        ans -= 2
                    if y < col - 1 and grid[x][y+1] == 1:
                        ans -= 2
​
        return ans
```
#### Notes
- scan from top to bottom, left to right, minus 2 when find adjection.
- time complexity: O(rows*cols)