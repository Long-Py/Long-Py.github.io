---
layout: post
title: '204. Count Primes'
subtitle: ''
date: 2019-08-29
categories: Leetcode
tags: Leetcode HashTable Math
---
### [204\. Count Primes](https://leetcode.com/problems/count-primes/)

Difficulty: **Easy**

Topics: **HashTable**


Count the number of prime numbers less than a non-negative number, **_n_**.

**Example:**

```
Input: 10
Output: 4
Explanation: There are 4 prime numbers less than 10, they are 2, 3, 5, 7.
```


#### Solution

Language: **Python**

```python
class Solution(object):
    def countPrimes(self, n):
        """
        :type n: int
        :rtype: int
        """
        if n < 3:
            return 0
        primes = [True] * n
        primes[0] = primes[1] = False
        for i in range(2, int(n ** 0.5) + 1):
            if primes[i]:
                primes[i * i: n: i] = [False] * len(primes[i * i: n: i])
        return sum(primes)
```
#### Notes
- The **Sieve of Eratosthenes** uses an extra O(n) memory and its runtime complexity is O(n log log n). For the more mathematically inclined readers, you can read more about its algorithm complexity on Wikipedia.