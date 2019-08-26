---
layout: post
title: '414. Third Maximum Number'
subtitle: ''
date: 2019-08-25
categories: Leetcode
tags: Leetcode Array
---
### [414\. Third Maximum Number](https://leetcode.com/problems/third-maximum-number/)

Difficulty: **Easy**

Topics: **Array**


Given a **non-empty** array of integers, return the **third** maximum number in this array. If it does not exist, return the maximum number. The time complexity must be in O(n).

**Example 1:**  

```
Input: [3, 2, 1]

Output: 1

Explanation: The third maximum is 1.
```

**Example 2:**  

```
Input: [1, 2]

Output: 2

Explanation: The third maximum does not exist, so the maximum (2) is returned instead.
```

**Example 3:**  

```
Input: [2, 2, 3, 1]

Output: 1

Explanation: Note that the third maximum here means the third maximum distinct number.
Both numbers with value 2 are both considered as second maximum.
```


#### Solution

Language: **Python**

```python
class Solution(object):
    def thirdMax(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        first_max = second_max = third_max = float('-inf')
        nums = set(nums)
        for n in nums:
            if n >= first_max:
                third_max = second_max
                second_max = first_max
                first_max = n
            elif n >= second_max:
                third_max = second_max
                second_max = n
            elif n >= third_max:
                third_max = n
        return third_max if third_max != float('-inf') else first_max
            elif n >= third_max:
```

#### Notes
- remove duplicated
- track 1st, 2nd, and 3rd largest values