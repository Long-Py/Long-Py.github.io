---
layout: post
title: '989. Add to Array-Form of Integer'
subtitle: ''
date: 2019-08-21
categories: Leetcode
tags: Leetcode Array
---
### [989\. Add to Array-Form of Integer](https://leetcode.com/problems/add-to-array-form-of-integer/)

Difficulty: **Easy**

Topics: **Array**

For a non-negative integer `X`, the _array-form of `X`_ is an array of its digits in left to right order.  For example, if `X = 1231`, then the array form is `[1,2,3,1]`.

Given the array-form `A` of a non-negative integer `X`, return the array-form of the integer `X+K`.


**Example 1:**

```
Input: A = [1,2,0,0], K = 34
Output: [1,2,3,4]
Explanation: 1200 + 34 = 1234
```


**Example 2:**

```
Input: A = [2,7,4], K = 181
Output: [4,5,5]
Explanation: 274 + 181 = 455
```


**Example 3:**

```
Input: A = [2,1,5], K = 806
Output: [1,0,2,1]
Explanation: 215 + 806 = 1021
```


**Example 4:**

```
Input: A = [9,9,9,9,9,9,9,9,9,9], K = 1
Output: [1,0,0,0,0,0,0,0,0,0,0]
Explanation: 9999999999 + 1 = 10000000000
```

**Note：**

1.  `1 <= A.length <= 10000`
2.  `0 <= A[i] <= 9`
3.  `0 <= K <= 10000`
4.  If `A.length > 1`, then `A[0] != 0`


#### Solution

Language: **Python**

```python
class Solution(object):
    def addToArrayForm(self, A, K):
        """
        :type A: List[int]
        :type K: int
        :rtype: List[int]
        """
        for i in range(len(A)-1,-1,-1):
            s = A[i]+K
            if K:
                A[i] = s%10
                K = s//10
        l = []
        while K:
            l.append(K%10)
            K /= 10 
        return l[::-1] + A
```

#### Notes
- notice: add rest K **reversed** before A
- time complexity: O(max(A, K))