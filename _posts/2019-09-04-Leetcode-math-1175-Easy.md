---
layout: post
title: '1175. Prime Arrangements'
subtitle: ''
date: 2019-09-03
categories: Leetcode
tags: Leetcode Math
---
### [1175\. Prime Arrangements](https://leetcode.com/problems/prime-arrangements/)

Difficulty: **Easy**

Topics: **Math**

Return the number of permutations of 1 to `n` so that prime numbers are at prime indices (1-indexed.)

_(Recall that an integer is prime if and only if it is greater than 1, and cannot be written as a product of two positive integers both smaller than it.)_

Since the answer may be large, return the answer **modulo `10^9 + 7`**.

**Example 1:**

```
Input: n = 5
Output: 12
Explanation: For example [1,2,5,4,3] is a valid permutation, but [5,2,3,4,1] is not because the prime number 5 is at index 1.
```

**Example 2:**

```
Input: n = 100
Output: 682289015
```

**Constraints:**

*   `1 <= n <= 100`


#### Solution

Language: **Python**

```python
class Solution(object):
    def numPrimeArrangements(self, n):
        """
        :type n: int
        :rtype: int
        """
        prime = [True for _ in range(n + 1)]
        p = 2
        while p * p <= n:
            if prime[p]:
                for i in range(p * p, n + 1, p):
                    prime[i] = False
            p += 1
        primes = sum(prime[2:])
        return math.factorial(primes) * math.factorial(n - primes) % (10 ** 9 + 7)
```
#### Notes
- [Sieve of Eratosthenes](https://en.wikipedia.org/wiki/Sieve_of_Eratosthenes)