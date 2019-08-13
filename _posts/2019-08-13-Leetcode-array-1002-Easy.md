---
layout: post
title: '1002. Find Common Characters'
subtitle: ''
date: 2019-08-13
categories: Leetcode
tags: Leetcode Array
---
### [1002\. Find Common Characters](https://leetcode.com/problems/find-common-characters/)

Difficulty: **Easy**

Topics: **Array**

Given an array `A` of strings made only from lowercase letters, return a list of all characters that show up in all strings within the list **(including duplicates)**.  For example, if a character occurs 3 times in all strings but not 4 times, you need to include that character three times in the final answer.

You may return the answer in any order.


**Example 1:**

```
Input: ["bella","label","roller"]
Output: ["e","l","l"]
```


**Example 2:**

```
Input: ["cool","lock","cook"]
Output: ["c","o"]
```

**<span style="display: inline;">Note:</span>**

1.  `1 <= A.length <= 100`
2.  `1 <= A[i].length <= 100`
3.  `A[i][j]` is a lowercase letter


#### Solution

Language: **Python**

```python
class Solution(object):
    def commonChars(self, A):
        """
        :type A: List[str]
        :rtype: List[str]
        """
        res = collections.Counter(A[0])
        for i in range(1,len(A)):
            res &= collections.Counter(A[i])
        
        return list(res.elements())
```

#### Notes
- `collections.Counter()`: Counter is a container that keeps track of how many times equivalent values are added. It can be used to implement the same algorithms for which bag or multiset data structures are commonly used in other languages.
- Counter's **Arithmetic**: 
  ```python
  import collections

  c1 = collections.Counter(['a', 'b', 'c', 'a', 'b', 'b'])
  c2 = collections.Counter('alphabet')

  print('Combined counts:')
  print(c1 + c2)
  
  print('Subtraction:')
  print(c1 - c2)

  print('Intersection (taking positive minimums):')
  print(c1 & c2)

  print('Union (taking maximums):')
  print(c1 | c2)
  ```
- Time Complexity: O(len(A)*len(string))