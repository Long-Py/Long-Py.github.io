---
layout: post
title: '840. Magic Squares In Grid'
subtitle: ''
date: 2019-08-23
categories: Leetcode
tags: Leetcode Array
---
### [840\. Magic Squares In Grid](https://leetcode.com/problems/magic-squares-in-grid/)

Difficulty: **Easy**

Topics: **Array**


A 3 x 3 magic square is a 3 x 3 grid filled with distinct numbers **from 1 to 9** such that each row, column, and both diagonals all have the same sum.

Given an `grid` of integers, how many 3 x 3 "magic square" subgrids are there?  (Each subgrid is contiguous).

**Example 1:**

```
Input: [[4,3,8,4],
        [9,5,1,9],
        [2,7,6,2]]
Output: 1
Explanation: 
The following subgrid is a 3 x 3 magic square:
438
951
276

while this one is not:
384
519
762

In total, there is only one magic square inside the given grid.
```

**Note:**

1.  `1 <= grid.length <= 10`
2.  `1 <= grid[0].length <= 10`
3.  `0 <= grid[i][j] <= 15`


#### Solution

Language: **Python**

```python
class Solution(object):
    def numMagicSquaresInside(self, grid):
        """
        :type grid: List[List[int]]
        :rtype: int
        """
        R, C = len(grid), len(grid[0])
​
        def magic(a,b,c,d,e,f,g,h,i):
            return (sorted([a,b,c,d,e,f,g,h,i]) == range(1, 10) and
                (a+b+c == d+e+f == g+h+i == a+d+g ==
                 b+e+h == c+f+i == a+e+i == c+e+g == 15))
​
        ans = 0
        for r in xrange(R-2):
            for c in xrange(C-2):
                if grid[r+1][c+1] != 5: continue  # optional skip
                if magic(grid[r][c], grid[r][c+1], grid[r][c+2],
                         grid[r+1][c], grid[r+1][c+1], grid[r+1][c+2],
                         grid[r+2][c], grid[r+2][c+1], grid[r+2][c+2]):
                    ans += 1
        return ans        
```

#### Notes
- brute force
- only one optimization:  cental of the square must be 5
- time complexity: O(R*C)