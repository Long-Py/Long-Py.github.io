---
layout: post
title: '1037. Valid Boomerang'
subtitle: ''
date: 2019-09-09
categories: Leetcode
tags: Leetcode Math
---
### [1037\. Valid Boomerang](https://leetcode.com/problems/valid-boomerang/)

Difficulty: **Easy**

Topics: **Math**


A _boomerang_ is a set of 3 points that are all distinct and **not** in a straight line.

Given a list of three points in the plane, return whether these points are a boomerang.

**Example 1:**

```
Input: [[1,1],[2,3],[3,2]]
Output: true
```


**Example 2:**

```
Input: [[1,1],[2,2],[3,3]]
Output: false
```


**Note:**

1.  `points.length == 3`
2.  `points[i].length == 2`
3.  `0 <= points[i][j] <= 100`


#### Solution

Language: **Python**

```python
class Solution(object):
    def isBoomerang(self, points):
        """
        :type points: List[List[int]]
        :rtype: bool
        """
        return (points[0][0] - points[1][0]) * (points[0][1] - points[2][1]) != (points[0][0] - points[2][0]) * (points[0][1] - points[1][1]);
```

#### Notes
- Calculate the slope of AB and AC
    
    K_AB = (p[0][0] - p[1][0]) / (p[0][1] - p[1][1])

    K_AC = (p[0][0] - p[2][0]) / (p[0][1] - p[2][1])

    We check if K_AB != K_AC, instead of calculate a fraction.