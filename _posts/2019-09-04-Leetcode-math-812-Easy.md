---
layout: post
title: '812. Largest Triangle Area'
subtitle: ''
date: 2019-09-03
categories: Leetcode
tags: Leetcode Math Array
---
### [812\. Largest Triangle Area](https://leetcode.com/problems/largest-triangle-area/)

Difficulty: **Easy**

Topics: **Math**


You have a list of points in the plane. Return the area of the largest triangle that can be formed by any 3 of the points.

```
Example:
Input: points = [[0,0],[0,1],[1,0],[0,2],[2,0]]
Output: 2
Explanation: 
The five points are show in the figure below. The red triangle is the largest.
```

![](https://s3-lc-upload.s3.amazonaws.com/uploads/2018/04/04/1027.png)

**Notes:**

*   `3 <= points.length <= 50`.
*   No points will be duplicated.
*   `-50 <= points[i][j] <= 50`.
*   Answers within `10^-6` of the true value will be accepted as correct.


#### Solution

Language: **Python**

```python
class Solution(object):
    def largestTriangleArea(self, points):
        """
        :type points: List[List[int]]
        :rtype: float
        """
        return max(0.5 * abs(i[0] * j[1] + j[0] * k[1] + k[0] * i[1]- j[0] * i[1] - k[0] * j[1] - i[0] * k[1]) for i, j, k in itertools.combinations(points, 3))
```

#### Notes
- brute force, time complexity: O(N^3)
![](https://s3-lc-upload.s3.amazonaws.com/users/lee215/image_1523209147.png)
![](https://s3-lc-upload.s3.amazonaws.com/users/lee215/image_1523379988.png)