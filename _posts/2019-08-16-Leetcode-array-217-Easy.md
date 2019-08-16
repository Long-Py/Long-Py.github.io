---
layout: post
title: '217. Contains Duplicate'
subtitle: ''
date: 2019-08-16
categories: Leetcode
tags: Leetcode Array
---
### [217\. Contains Duplicate](https://leetcode.com/problems/contains-duplicate/)

Difficulty: **Easy**

Topics: **Array**


Given an array of integers, find if the array contains any duplicates.

Your function should return true if any value appears at least twice in the array, and it should return false if every element is distinct.

**Example 1:**

```
Input: [1,2,3,1]
Output: true
```

**Example 2:**

```
Input: [1,2,3,4]
Output: false
```

**Example 3:**

```
Input: [1,1,1,3,3,4,3,2,4,2]
Output: true
```


#### Solution

Language: **Python**

```python
class Solution(object):
    def containsDuplicate(self, nums):
        """
        :type nums: List[int]
        :rtype: bool
        """
        return len(set(nums)) != len(nums)
```

#### Notes
- length of set does not equal to length of list then we have duplicate in list