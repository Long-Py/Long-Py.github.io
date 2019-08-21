---
layout: post
title: '118. Pascal Triangle'
subtitle: ''
date: 2019-08-20
categories: Leetcode
tags: Leetcode Array
---

### [118\. Pascal\'s Triangle](https://leetcode.com/problems/pascals-triangle/)

Difficulty: **Easy**

Topics: **Array**


Given a non-negative integer _numRows_, generate the first _numRows_ of Pascal's triangle.

![](https://upload.wikimedia.org/wikipedia/commons/0/0d/PascalTriangleAnimated2.gif)  
<small style="display: inline;">In Pascal's triangle, each number is the sum of the two numbers directly above it.</small>

**Example:**

```
Input: 5
Output:
[
     [1],
    [1,1],
   [1,2,1],
  [1,3,3,1],
 [1,4,6,4,1]
]
```


#### Solution

Language: **Python**

```python
class Solution(object):
    def generate(self, numRows):
        """
        :type numRows: int
        :rtype: List[List[int]]
        """
        if not numRows: return []
        if numRows == 1: return [[1]]
        if numRows == 2: return [[1],[1,1]]
        ans = [[1],[1,1]]
        for i in range(2,numRows):
            cur = [1]*(i+1)
            for j in range(1,len(cur)-1):
                cur[j] = ans[i-1][j-1] + ans[i-1][j]
            ans.append(cur)
        return ans
```
#### Notes
- notice: `range(2,numRows)` and `cur = [1]*(i+1)`
