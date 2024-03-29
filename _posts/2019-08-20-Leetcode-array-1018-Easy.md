---
layout: post
title: '1018. Binary Prefix Divisible By 5'
subtitle: ''
date: 2019-08-20
categories: Leetcode
tags: Leetcode Array
---
### [1018\. Binary Prefix Divisible By 5](https://leetcode.com/problems/binary-prefix-divisible-by-5/)

Difficulty: **Easy**

Topics: **Array**


Given an array `A` of `0`s and `1`s, consider `N_i`: the i-th subarray from `A[0]` to `A[i]` interpreted as a binary number (from most-significant-bit to least-significant-bit.)

Return a list of booleans `answer`, where `answer[i]` is `true` if and only if `N_i` is divisible by 5.

**Example 1:**

```
Input: [0,1,1]
Output: [true,false,false]
Explanation: 
The input numbers in binary are 0, 01, 011; which are 0, 1, and 3 in base-10\.  Only the first number is divisible by 5, so answer[0] is true.
```

**Example 2:**

```
Input: [1,1,1]
Output: [false,false,false]
```

**Example 3:**

```
Input: [0,1,1,1,1,1]
Output: [true,false,false,false,true,false]
```

**Example 4:**

```
Input: [1,1,1,0,1]
Output: [false,false,false,false,false]
```

**Note:**

1.  `1 <= A.length <= 30000`
2.  `A[i]` is `0` or `1`


#### Solution

Language: **Python**

```python
class Solution(object):
    def prefixesDivBy5(self, A):
        """
        :type A: List[int]
        :rtype: List[bool]
        """
        d = 0
        ans = []
        for n in A:
            d = d*2 + n
            ans.append(d%5==0)
        return ans
```

#### Notes
- If X is the first i digits of the array as a binary number, then 2X + A[i] is the first i+1 digits. Just like bit manipulation `i << 1`.