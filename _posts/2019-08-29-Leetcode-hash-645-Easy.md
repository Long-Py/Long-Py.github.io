---
layout: post
title: '645. Set Mismatch'
subtitle: ''
date: 2019-08-29
categories: Leetcode
tags: Leetcode Array HashTable Math
---
### [645\. Set Mismatch](https://leetcode.com/problems/set-mismatch/)

Difficulty: **Easy**

Topics: **HashTable**


The set `S` originally contains numbers from 1 to `n`. But unfortunately, due to the data error, one of the numbers in the set got duplicated to **another** number in the set, which results in repetition of one number and loss of another number.

Given an array `nums` representing the data status of this set after the error. Your task is to firstly find the number occurs twice and then find the number that is missing. Return them in the form of an array.

**Example 1:**  

```
Input: nums = [1,2,2,4]
Output: [2,3]
```

**Note:**  

1.  The given array size will in the range [2, 10000].
2.  The given array's numbers won't have any order.


#### Solution

Language: **Python**

```python
class Solution(object):
    def findErrorNums(self, nums):
        """
        :type nums: List[int]
        :rtype: List[int]
        """
        cnt = collections.Counter(nums)
        ans = [None]*2
        for i in range(1, len(nums)+1):
            if i in cnt:
                if cnt[i] == 2:
                    ans[0] = i
            else:
                ans[1] = i
        return ans
        
```
#### Notes
- time complexity: O(n)