---
layout: post
title: '686. Repeated String Match'
subtitle: ''
date: 2019-08-25
categories: Leetcode
tags: Leetcode Strings
---

### [686\. Repeated String Match](https://leetcode.com/problems/repeated-string-match/)

Difficulty: **Easy**

Topics: **Strings**

Given two strings A and B, find the minimum number of times A has to be repeated such that B is a substring of it. If no such solution, return -1.

For example, with A = "abcd" and B = "cdabcdab".

Return 3, because by repeating A three times (“abcdabcdabcd”), B is a substring of it; and B is not a substring of A repeated two times ("abcdabcd").

**Note:**  
The length of `A` and `B` will be between 1 and 10000.


#### Solution

Language: **Python**

```python
class Solution(object):
    def repeatedStringMatch(self, A, B):
        """
        :type A: str
        :type B: str
        :rtype: int
        """
        times = -(-len(B) // len(A)) # Equal to ceil(len(b) / len(a))
        for i in range(2):
            if B in (A * (times + i)):
                return times + i
        return -1
        
```

#### Notes
- `ceil()` returns ceiling value of x - the smallest integer not less than x.
- The answer n can only be x or x + 1 (in the case where len(B) is a multiple of len(A) like in A = "abcd" and B = "cdabcdab") and not more. Because if B is already in A * n, B is definitely in A * (n + 1).