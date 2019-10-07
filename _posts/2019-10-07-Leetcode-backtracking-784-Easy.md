---
layout: post
title: '784. Letter Case Permutation'
subtitle: ''
date: 2019-10-07
categories: Leetcode
tags: Leetcode Backtracking
---
### [784\. Letter Case Permutation](https://leetcode.com/problems/letter-case-permutation/)

Difficulty: **Easy**

Topics: **Backtracking**


Given a string S, we can transform every letter individually to be lowercase or uppercase to create another string.  Return a list of all possible strings we could create.

```
Examples:
Input: S = "a1b2"
Output: ["a1b2", "a1B2", "A1b2", "A1B2"]

Input: S = "3z4"
Output: ["3z4", "3Z4"]

Input: S = "12345"
Output: ["12345"]
```

**Note:**

*   `S` will be a string with length between `1` and `12`.
*   `S` will consist only of letters or digits.


#### Solution

Language: **Python**

```python
class Solution(object):
    def letterCasePermutation(self, S):
        """
        :type S: str
        :rtype: List[str]
        """
        res = [S]
        for i, c in enumerate(S):
            if c.isalpha():
                res.extend([s[:i] + s[i].swapcase() + s[i+1:] for s in res])
        return res
```

### Notes
- The string `swapcase()` method converts all uppercase characters to lowercase and vice versa of the given string, and returns it.
- `Append()`: Adds its argument as a single element to the end of a list. The length of the list increases by one.
- `extend()`: Iterates over its argument and adding each element to the list and extending the list. The length of the list increases by number of elements in it’s argument.
