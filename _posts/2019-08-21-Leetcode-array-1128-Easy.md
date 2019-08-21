---
layout: post
title: '1128. Number of Equivalent Domino Pairs'
subtitle: ''
date: 2019-08-21
categories: Leetcode
tags: Leetcode Array
---
### [1128\. Number of Equivalent Domino Pairs](https://leetcode.com/problems/number-of-equivalent-domino-pairs/)

Difficulty: **Easy**

Topics: **Array**

Given a list of `dominoes`, `dominoes[i] = [a, b]` is _equivalent_ to `dominoes[j] = [c, d]` if and only if either (`a==c` and `b==d`), or (`a==d` and `b==c`) - that is, one domino can be rotated to be equal to another domino.

Return the number of pairs `(i, j)` for which `0 <= i < j < dominoes.length`, and `dominoes[i]` is equivalent to `dominoes[j]`.

**Example 1:**

```
Input: dominoes = [[1,2],[2,1],[3,4],[5,6]]
Output: 1
```

**Constraints:**

*   `1 <= dominoes.length <= 40000`
*   `1 <= dominoes[i][j] <= 9`


#### Solution

Language: **Python**

```python
class Solution(object):
    def numEquivDominoPairs(self, dominoes):
        """
        :type dominoes: List[List[int]]
        :rtype: int
        """
        d = {}
        for i,j in dominoes:
            if i < j:
                d[(i,j)] = d.get((i,j), 0) + 1
            else:
                d[(j,i)] = d.get((j,i), 0) + 1
        
        return sum(i*(i-1)//2 for i in d.values())
```

#### Notes
- count sorted pairs and put into dict