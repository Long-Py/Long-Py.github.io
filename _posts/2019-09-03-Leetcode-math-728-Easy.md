---
layout: post
title: '728. Self Dividing Numbers'
subtitle: ''
date: 2019-09-03
categories: Leetcode
tags: Leetcode Math Array
---
### [728\. Self Dividing Numbers](https://leetcode.com/problems/self-dividing-numbers/)

Difficulty: **Easy**

Topics: **Math**


A _self-dividing number_ is a number that is divisible by every digit it contains.

For example, 128 is a self-dividing number because `128 % 1 == 0`, `128 % 2 == 0`, and `128 % 8 == 0`.

Also, a self-dividing number is not allowed to contain the digit zero.

Given a lower and upper number bound, output a list of every possible self dividing number, including the bounds if possible.

**Example 1:**  

```
Input: 
left = 1, right = 22
Output: [1, 2, 3, 4, 5, 6, 7, 8, 9, 11, 12, 15, 22]
```

**Note:**

*   The boundaries of each input argument are `1 <= left <= right <= 10000`.

#### Solution

Language: **Python**

```python
class Solution(object):
    def selfDividingNumbers(self, left, right):
        """
        :type left: int
        :type right: int
        :rtype: List[int]
        """
        ans = []
        for n in range(left,right+1):
            cur = list(map(int,str(n)))
            if 0 in cur:
                continue
            if all(n%i==0 for i in cur):
                ans.append(n)
        return ans
```

#### Notes
- time complexity: O(m*n)