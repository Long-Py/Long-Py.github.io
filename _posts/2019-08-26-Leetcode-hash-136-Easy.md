---
layout: post
title: '136. Single Number'
subtitle: ''
date: 2019-08-26
categories: Leetcode
tags: Leetcode Array HashTable
---
### [136\. Single Number](https://leetcode.com/problems/single-number/)

Difficulty: **Easy**

Topics: **HashTable**


Given a **non-empty** array of integers, every element appears _twice_ except for one. Find that single one.

**Note:**

Your algorithm should have a linear runtime complexity. Could you implement it without using extra memory?

**Example 1:**

```
Input: [2,2,1]
Output: 1
```

**Example 2:**

```
Input: [4,1,2,1,2]
Output: 4
```


#### Solution

Language: **Python**

```python
class Solution(object):
    def singleNumber(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        d = collections.Counter(nums)
        for n, c in d.items():
            if c == 1:
                return n
        
        
        
```
#### Notes
- can also use bit manipulation: `ans ^= n for n in nums`