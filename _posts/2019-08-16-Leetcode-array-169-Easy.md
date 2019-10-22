---
layout: post
title: '169. Majority Element'
subtitle: ''
date: 2019-08-16
categories: Leetcode
tags: Leetcode Array Divide&Conquer BitManipulation
---

### [169\. Majority Element](https://leetcode.com/problems/majority-element/)

Difficulty: **Easy**

Topics: **Array**


Given an array of size _n_, find the majority element. The majority element is the element that appears **more than** `⌊ n/2 ⌋` times.

You may assume that the array is non-empty and the majority element always exist in the array.

**Example 1:**

```
Input: [3,2,3]
Output: 3
```

**Example 2:**

```
Input: [2,2,1,1,1,2,2]
Output: 2
```


#### Solution

Language: **Python**

```python
class Solution(object):
    def majorityElement(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        cnts = collections.Counter(nums)
        return max(cnts.keys(), key=cnts.get)
```

#### Notes
- create Counter object then get the key with biggest value
- `keys()` access a list of all keys in a dict
- `get()` access a value for a key