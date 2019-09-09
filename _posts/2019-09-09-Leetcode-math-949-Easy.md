---
layout: post
title: '949. Largest Time for Given Digits'
subtitle: ''
date: 2019-09-09
categories: Leetcode
tags: Leetcode Math Array
---
### [949\. Largest Time for Given Digits](https://leetcode.com/problems/largest-time-for-given-digits/)

Difficulty: **Easy**

Topics: **Math**


Given an array of 4 digits, return the largest 24 hour time that can be made.

The smallest 24 hour time is 00:00, and the largest is 23:59.  Starting from 00:00, a time is larger if more time has elapsed since midnight.

Return the answer as a string of length 5.  If no valid time can be made, return an empty string.


**Example 1:**

```
Input: [1,2,3,4]
Output: "23:41"
```


**Example 2:**

```
Input: [5,5,5,5]
Output: ""
```

**<span style="display: inline;">Note:</span>**

1.  `A.length == 4`
2.  `0 <= A[i] <= 9`


#### Solution

Language: **Python**

```python
class Solution(object):
    def largestTimeFromDigits(self, A):
        """
        :type A: List[int]
        :rtype: str
        """
        ans = -1
        for h1, h2, m1, m2 in itertools.permutations(A):
            hours = 10 * h1 + h2
            mins = 10 * m1 + m2
            time = 60 * hours + mins
            if 0 <= hours < 24 and 0 <= mins < 60 and time > ans:
                ans = time
​
        return "{:02}:{:02}".format(*divmod(ans, 60)) if ans >= 0 else ""        
```
#### Notes
- `itertools.permutations()`: [Permutation and Combination in Python](https://www.geeksforgeeks.org/permutation-and-combination-in-python/)