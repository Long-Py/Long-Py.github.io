---
layout: post
title: '278. First Bad Version'
subtitle: ''
date: 2019-09-11
categories: Leetcode
tags: Leetcode BinarySearch
---
### [278\. First Bad Version](https://leetcode.com/problems/first-bad-version/)

Difficulty: **Easy**

Topics: **Binary Search**


You are a product manager and currently leading a team to develop a new product. Unfortunately, the latest version of your product fails the quality check. Since each version is developed based on the previous version, all the versions after a bad version are also bad.

Suppose you have `n` versions `[1, 2, ..., n]` and you want to find out the first bad one, which causes all the following ones to be bad.

You are given an API `bool isBadVersion(version)` which will return whether `version` is bad. Implement a function to find the first bad version. You should minimize the number of calls to the API.

**Example:**

```
Given n = 5, and version = 4 is the first bad version.

call isBadVersion(3) -> false
call isBadVersion(5) -> true
call isBadVersion(4) -> true

Then 4 is the first bad version. 
```


#### Solution

Language: **Python**

```python
# The isBadVersion API is already defined for you.
# @param version, an integer
# @return a bool
# def isBadVersion(version):
​
class Solution(object):
    def firstBadVersion(self, n):
        """
        :type n: int
        :rtype: int
        """
        l, r = 1, n
        while l <= r:
            mid = l + (r-l)//2
            if isBadVersion(mid):
                r = mid - 1
            else:
                l = mid + 1
        return l 
```

#### Notes
- cant return mid directly, when `True`