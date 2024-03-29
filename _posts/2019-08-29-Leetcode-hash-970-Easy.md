---
layout: post
title: '970. Powerful Integers'
subtitle: ''
date: 2019-08-29
categories: Leetcode
tags: Leetcode HashTable Math
---
### [970\. Powerful Integers](https://leetcode.com/problems/powerful-integers/)

Difficulty: **Easy**

Topics: **HashTable**

Given two positive integers `x` and `y`, an integer is _powerful_ if it is equal to `x^i + y^j` for some integers `i >= 0` and `j >= 0`.

Return a list of all _powerful_ integers that have value less than or equal to `bound`.

You may return the answer in any order.  In your answer, each value should occur at most once.


**Example 1:**

```
Input: x = 2, y = 3, bound = 10
Output: [2,3,4,5,7,9,10]
Explanation: 
2 = 2^0 + 3^0
3 = 2^1 + 3^0
4 = 2^0 + 3^1
5 = 2^1 + 3^1
7 = 2^2 + 3^1
9 = 2^3 + 3^0
10 = 2^0 + 3^2
```


**Example 2:**

```
Input: x = 3, y = 5, bound = 15
Output: [2,4,6,8,10,14]
```


**Note:**

*   `1 <= x <= 100`
*   `1 <= y <= 100`
*   `0 <= bound <= 10^6`


#### Solution

Language: **Python**

```python
class Solution(object):
    def powerfulIntegers(self, x, y, bound):
        """
        :type x: int
        :type y: int
        :type bound: int
        :rtype: List[int]
        """
        ans = set()
        # 2**20 > 10^6
        for i in xrange(20):
            for j in xrange(20):
                v = x**i + y**j
                if v <= bound:
                    ans.add(v)
        return list(ans)
        
```
#### Notes
- Time Complexity: O(log<sub>2</sub><sup>bound</sup>)