---
layout: post
title: '859. Buddy Strings'
subtitle: ''
date: 2019-08-25
categories: Leetcode
tags: Leetcode Strings
---
### [859\. Buddy Strings](https://leetcode.com/problems/buddy-strings/)

Difficulty: **Easy**

Topics: **Strings**

Given two strings `A` and `B` of lowercase letters, return `true` if and only if we can swap two letters in `A` so that the result equals `B`.

**Example 1:**


```
Input: A = "ab", B = "ba"
Output: true
```


**Example 2:**

```
Input: A = "ab", B = "ab"
Output: false
```


**Example 3:**

```
Input: A = "aa", B = "aa"
Output: true
```


**Example 4:**

```
Input: A = "aaaaaaabc", B = "aaaaaaacb"
Output: true
```


**Example 5:**

```
Input: A = "", B = "aa"
Output: false
```

**<span style="display: inline;">Note:</span>**

1.  `0 <= A.length <= 20000`
2.  `0 <= B.length <= 20000`
3.  `A` and `B` consist only of lowercase letters.


#### Solution

Language: **Python**

```python
class Solution(object):
    def buddyStrings(self, A, B):
        """
        :type A: str
        :type B: str
        :rtype: bool
        """
        a = len(A)
        b = len(B)
        if a != b: return False
        if A == B and len(set(A)) < a: return True
        dif = [(a,b) for a,b in zip(A,B) if a != b]
        return len(dif) == 2 and dif[0] == dif[1][::-1]
```

#### Notes
- if length differs or set of characters differ, return False directly
- if A and B are equal, returns if we have at least 1 repetitive character in the list
- if two list have more than 2 indices with different characters, return false
- In the end check if the swap can happen
