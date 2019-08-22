---
layout: post
title: '38. Count and Say'
subtitle: ''
date: 2019-08-22
categories: Leetcode
tags: Leetcode Strings
---
### [38\. Count and Say](https://leetcode.com/problems/count-and-say/)

Difficulty: **Easy**

Topics: **Strings**


The count-and-say sequence is the sequence of integers with the first five terms as following:

```
1.     1
2.     11
3.     21
4.     1211
5.     111221
```

`1` is read off as `"one 1"` or `11`.  
`11` is read off as `"two 1s"` or `21`.  
`21` is read off as `"one 2`, then `one 1"` or `1211`.

Given an integer _n_ where 1 ≤ _n_ ≤ 30, generate the _n_<sup>th</sup> term of the count-and-say sequence.

Note: Each term of the sequence of integers will be represented as a string.

**Example 1:**

```
Input: 1
Output: "1"
```

**Example 2:**

```
Input: 4
Output: "1211"
```


#### Solution

Language: **Python**

```python
class Solution(object):
    def countAndSay(self, n):
        """
        :type n: int
        :rtype: str
        """
        ans = "1"
        if n == 1: return ans
        for i in range(n-1):
            cur = ''
            grps = itertools.groupby(ans)
            for c, g in grps:
                cur += c + str(len(list(g)))
            ans = cur
        return ans[::-1]
```

#### Notes
- use *group by*
- for loop: `n-1`
- return **reversed** ans