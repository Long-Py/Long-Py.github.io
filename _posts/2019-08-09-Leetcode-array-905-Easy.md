---
layout: post
title: '905. Sort Array By Parity'
subtitle: ''
date: 2019-08-09
categories: Leetcode
tags: Leetcode Array
---

### [905\. Sort Array By ParityCopy for MarkdownCopy for MarkdownCopy for MarkdownCopy for MarkdownCopy for Markdown](https://leetcode.com/problems/sort-array-by-parity/)

Difficulty: **Easy**

Topics: **Array**


Given an array `A` of non-negative integers, return an array consisting of all the even elements of `A`, followed by all the odd elements of `A`.

You may return any answer array that satisfies this condition.


**Example 1:**

```
Input: [3,1,2,4]
Output: [2,4,3,1]
The outputs [4,2,3,1], [2,4,1,3], and [4,2,1,3] would also be accepted.
```

**Note:**

1.  `1 <= A.length <= 5000`
2.  `0 <= A[i] <= 5000`


#### Solution1

Language: **Python**

```python
class Solution1(object):
    def sortArrayByParity(self, A):
        """
        :type A: List[int]
        :rtype: List[int]
        """
        left, right = 0, len(A)-1
        while left < right:
            if A[left]%2 != 0 and A[right]%2 == 0:
                A[left], A[right] = A[right], A[left]
                left += 1
                right -= 1
            elif A[left]%2 == 0:
                left += 1
            else:
                right -= 1
        return A
```

#### Solution2

Language: **Python**

```python
class Solution2(object):
    def sortArrayByParity(self, A):
        """
        :type A: List[int]
        :rtype: List[int]
        """
        return sorted(A, key = lambda x : x % 2)
```

#### Notes
- solution1: two pointers
- solution2: sorted by *key function*

  Both `list.sort()` and `sorted()` have a `key` parameter to specify a function to be called on each list element prior to making comparisons.