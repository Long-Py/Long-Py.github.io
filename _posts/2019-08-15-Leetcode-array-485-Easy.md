---
layout: post
title: '485. Max Consecutive Ones'
subtitle: ''
date: 2019-08-15
categories: Leetcode
tags: Leetcode Array
---
### [485\. Max Consecutive Ones](https://leetcode.com/problems/max-consecutive-ones/)

Difficulty: **Easy**

Topics: **Array**


Given a binary array, find the maximum number of consecutive 1s in this array.

**Example 1:**  

```
Input: [1,1,0,1,1,1]
Output: 3
Explanation: The first two digits or the last three digits are consecutive 1s.
    The maximum number of consecutive 1s is 3.
```

**Note:**

*   The input array will only contain `0` and `1`.
*   The length of input array is a positive integer and will not exceed 10,000


#### Solution

Language: **Python**

```python
class Solution(object):
    def findMaxConsecutiveOnes(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        cur, res = 0, 0
        for i,v in enumerate(nums):
            if v != 1:
                res = max(res, cur)
                cur = 0
            else:
                cur += 1
                if cur > res:
                    res = cur
        return res
```

#### Notes
- scan the list, when meet 0 set `cur` to 0 and compare value between `cur` and `res`, when meet 1 inscrease `cur` by 1 if `cur` > `res` set `cur` to `res`.
- Time complexity: O(n)