---
layout: post
title: '119. Pascal's Triangle II'
subtitle: ''
date: 2019-08-21
categories: Leetcode
tags: Leetcode Array
---
### [119\. Pascal's Triangle II](https://leetcode.com/problems/pascals-triangle-ii/)

Difficulty: **Easy**

Topics: **Array**

Given a non-negative index _k_ where _k_ ≤ 33, return the _k_<sup>th</sup> index row of the Pascal's triangle.

Note that the row index starts from 0.

**Example:**

```
Input: 3
Output: [1,3,3,1]
```

**Follow up:**

Could you optimize your algorithm to use only _O_(_k_) extra space?


#### Solution

Language: **Python**

```python
class Solution(object):
    def getRow(self, rowIndex):
        """
        :type rowIndex: int
        :rtype: List[int]
        """
        ans = []
        for i in range(rowIndex+1):
            cur = [1] *(i+1)
            for j in range(1,i):
                cur[j] = ans[j-1]+ans[j]
            ans = cur
        return ans
```
#### Notes
- imporve from *Pascal's Triangle I*, but for this problem, only track the result of prev line.