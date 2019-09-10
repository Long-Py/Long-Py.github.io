---
layout: post
title: '754. Reach a Number'
subtitle: ''
date: 2019-09-09
categories: Leetcode
tags: Leetcode Math
---
### [754\. Reach a Number](https://leetcode.com/problems/reach-a-number/)

Difficulty: **Easy**

Topics: **Math**

You are standing at position `0` on an infinite number line. There is a goal at position `target`.

On each move, you can either go left or right. During the _n_-th move (starting from 1), you take _n_ steps.

Return the minimum number of steps required to reach the destination.

**Example 1:**  

```
Input: target = 3
Output: 2
Explanation:
On the first move we step from 0 to 1.
On the second step we step from 1 to 3.
```

**Example 2:**  

```
Input: target = 2
Output: 3
Explanation:
On the first move we step from 0 to 1.
On the second move we step  from 1 to -1.
On the third move we step from -1 to 2.
```

**Note:**  

*   `target` will be a non-zero integer in the range `[-10^9, 10^9]`.

#### Solution

Language: **Python**

```python
class Solution(object):
    def reachNumber(self, target):
        """
        :type target: int
        :rtype: int
        """
        target = abs(target)
        n = int(math.ceil(math.sqrt(1 + 8 * target)/2 - 0.5))  # root of func
        while target % 2 != n * ( n + 1 ) / 2 % 2:  # both target and n are odd or even
            n += 1
        return n
        
```