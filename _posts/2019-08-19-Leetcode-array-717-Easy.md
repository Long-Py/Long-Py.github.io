---
layout: post
title: '717. 1-bit and 2-bit Characters'
subtitle: ''
date: 2019-08-19
categories: Leetcode
tags: Leetcode Array
---
### [717\. 1-bit and 2-bit Characters](https://leetcode.com/problems/1-bit-and-2-bit-characters/)

Difficulty: **Easy**

Topics: **Array**


We have two special characters. The first character can be represented by one bit `0`. The second character can be represented by two bits (`10` or `11`).

Now given a string represented by several bits. Return whether the last character must be a one-bit character or not. The given string will always end with a zero.

**Example 1:**  

```
Input: 
bits = [1, 0, 0]
Output: True
Explanation: 
The only way to decode it is two-bit character and one-bit character. So the last character is one-bit character.
```

**Example 2:**  

```
Input: 
bits = [1, 1, 1, 0]
Output: False
Explanation: 
The only way to decode it is two-bit character and two-bit character. So the last character is NOT one-bit character.
```

**Note:**

*   `1 <= len(bits) <= 1000`.*   `bits[i]` is always `0` or `1`.

#### Solution

Language: **Python**

```python
class Solution(object):
    def isOneBitCharacter(self, bits):
        """
        :type bits: List[int]
        :rtype: bool
        """
        idx = 0
        while idx < len(bits)-1:
            if bits[idx] == 1:
                idx += 2
            else:
                idx += 1
        return idx == len(bits)-1 and bits[idx] == 0
```

#### Notes
- increment pointer, when val is 1 inscrease pointer by 2, 0 by 1.
    then check pointer == len - 1 and last element is 0.