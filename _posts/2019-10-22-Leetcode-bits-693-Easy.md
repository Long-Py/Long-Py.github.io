---
layout: post
title: '693. Binary Number with Alternating Bits'
subtitle: ''
date: 2019-10-22
categories: Leetcode
tags: Leetcode BitManipulation
---
### [693\. Binary Number with Alternating Bits](https://leetcode.com/problems/binary-number-with-alternating-bits/)

Difficulty: **Easy**

Topics: **Bit Manipulation**

Given a positive integer, check whether it has alternating bits: namely, if two adjacent bits will always have different values.

**Example 1:**  

```
Input: 5
Output: True
Explanation:
The binary representation of 5 is: 101
```

**Example 2:**  

```
Input: 7
Output: False
Explanation:
The binary representation of 7 is: 111.
```

**Example 3:**  

```
Input: 11
Output: False
Explanation:
The binary representation of 11 is: 1011.
```

**Example 4:**  

```
Input: 10
Output: True
Explanation:
The binary representation of 10 is: 1010.
```


#### Solution

Language: **Python**

```python
class Solution(object):
    def hasAlternatingBits(self, n):
        """
        :type n: int
        :rtype: bool
        """
        return '00' not in bin(n) and '11' not in bin(n)
```

#### Notes

- bit manipulation method:
```python
    a = n ^ (n >> 1)
    return a & (a+1) == 0
```
    Explanation:
    Example: n = 7 (bin=101)

    Shifting n=7 one bit to the right results in 010; 101 ^ 010 = 111 = num
    If n would be true, num's bits would always 1. Adding 1 would turn all previous bits to zero and would add a new positive bit to the left. Example, bin(0111) + 1 =bin(1000). result = not bin(1000) & bin(0111) = bin(0000)