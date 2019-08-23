---
layout: post
title: '747. Largest Number At Least Twice of Others'
subtitle: ''
date: 2019-08-22
categories: Leetcode
tags: Leetcode Array
---
### [747\. Largest Number At Least Twice of Others](https://leetcode.com/problems/largest-number-at-least-twice-of-others/)

Difficulty: **Easy**

Topics: **Array**


In a given integer array `nums`, there is always exactly one largest element.

Find whether the largest element in the array is at least twice as much as every other number in the array.

If it is, return the **index** of the largest element, otherwise return -1.

**Example 1:**

```
Input: nums = [3, 6, 1, 0]
Output: 1
Explanation: 6 is the largest integer, and for every other number in the array x,
6 is more than twice as big as x.  The index of value 6 is 1, so we return 1.
```

**Example 2:**

```
Input: nums = [1, 2, 3, 4]
Output: -1
Explanation: 4 isn't at least as big as twice the value of 3, so we return -1.
```

**Note:**

1.  `nums` will have a length in the range `[1, 50]`.
2.  Every `nums[i]` will be an integer in the range `[0, 99]`.


#### Solution

Language: **Python**

```python
class Solution(object):
    def dominantIndex(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        first, second = -1, -1
        idx = 0
        for i, n in enumerate(nums):
            if n >= first:
                second = first
                first = n
                idx = i
            elif n > second:
                second = n
        return idx if first >= 2 * second else -1
    
        return i if first > 2 * second else -1
```

#### Notes
- One pass: keep track the largest number and the 2nd largest number.
- Two passes: 1st pass get the largest number; 2nd pass get the 2nd largets number.