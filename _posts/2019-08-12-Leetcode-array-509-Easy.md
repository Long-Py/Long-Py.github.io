---
layout: post
title: '509. Fibonacci Number'
subtitle: ''
date: 2019-08-12
categories: Leetcode
tags: Leetcode Array
---

### [509\. Fibonacci Number](https://leetcode.com/problems/fibonacci-number/)

Difficulty: **Easy**

Topics: **Array**


The **Fibonacci numbers**, commonly denoted `F(n)` form a sequence, called the **Fibonacci sequence**, such that each number is the sum of the two preceding ones, starting from `0` and `1`. That is,

```
F(0) = 0,   F(1) = 1
F(N) = F(N - 1) + F(N - 2), for N > 1.
```

Given `N`, calculate `F(N)`.

**Example 1:**

```
Input: 2
Output: 1
Explanation: F(2) = F(1) + F(0) = 1 + 0 = 1.
```

**Example 2:**

```
Input: 3
Output: 2
Explanation: F(3) = F(2) + F(1) = 1 + 1 = 2.
```

**Example 3:**

```
Input: 4
Output: 3
Explanation: F(4) = F(3) + F(2) = 2 + 1 = 3.
```

**Note:**

0 ≤ `N` ≤ 30.


#### Solution

Language: **Python**

```python
class Solution(object):
    def fib(self, N):
        """
        :type N: int
        :rtype: int
        """
        a,b = 0, 1
        
        for _ in range(N):
            a, b = b, a + b
        return a
```

#### Notes
- **Dynamic Programming** is mainly an optimization over plain recursion. Wherever we see a recursive solution that has **repeated calls** for same inputs, we can optimize it using Dynamic Programming. The idea is to simply store the results of subproblems, so that we do not have to re-compute them when needed later. This simple optimization reduces time complexities from exponential to polynomial. For example, if we write simple recursive solution for **Fibonacci Numbers**, we get exponential time complexity and if we optimize it by storing solutions of subproblems, time complexity reduces to linear.