---
layout: post
title: '191. Number of 1 Bits'
subtitle: ''
date: 2019-10-25
categories: Leetcode
tags: Leetcode BitManipulation
---

### [191\. Number of 1 Bits](https://leetcode.com/problems/number-of-1-bits/)

Difficulty: **Easy**

Topics: **Bit Manipulation**

Write a function that takes an unsigned integer and return the number of '1' bits it has (also known as the ).

**Example 1:**

```
Input: 00000000000000000000000000001011
Output: 3
Explanation: The input binary string 00000000000000000000000000001011 has a total of three '1' bits.
```

**Example 2:**

```
Input: 00000000000000000000000010000000
Output: 1
Explanation: The input binary string 00000000000000000000000010000000 has a total of one '1' bit.
```

**Example 3:**

```
Input: 11111111111111111111111111111101
Output: 31
Explanation: The input binary string 11111111111111111111111111111101 has a total of thirty one '1' bits.
```

**Note:**

*   Note that in some languages such as Java, there is no unsigned integer type. In this case, the input will be given as signed integer type and should not affect your implementation, as the internal binary representation of the integer is the same whether it is signed or unsigned.
*   In Java, the compiler represents the signed integers using . Therefore, in **Example 3** above the input represents the signed integer `-3`.

**Follow up**:

If this function is called many times, how would you optimize it?


#### Solution

Language: **Python**

```python
class Solution(object):
    def hammingWeight(self, n):
        """
        :type n: int
        :rtype: int
        """
        cnt = 0
        while n:
            n &= n - 1
            cnt += 1
        return cnt
```

#### Notes
- `n & (n - 1)` trick to remove the last 1