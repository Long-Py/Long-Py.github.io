---
layout: post
title: '844. Backspace String Compare'
subtitle: ''
date: 2019-09-10
categories: Leetcode
tags: Leetcode TwoPointers Stack
---
### [844\. Backspace String Compare](https://leetcode.com/problems/backspace-string-compare/)

Difficulty: **Easy**

Topics: **Two Pointers**

Given two strings `S` and `T`, return if they are equal when both are typed into empty text editors. `#` means a backspace character.


**Example 1:**

```
Input: S = "ab#c", T = "ad#c"
Output: true
Explanation: Both S and T become "ac".
```


**Example 2:**

```
Input: S = "ab##", T = "c#d#"
Output: true
Explanation: Both S and T become "".
```


**Example 3:**

```
Input: S = "a##c", T = "#a#c"
Output: true
Explanation: Both S and T become "c".
```


**Example 4:**

```
Input: S = "a#c", T = "b"
Output: false
Explanation: S becomes "c" while T becomes "b".
```

**Note**:

1.  `<span style="display: inline;">1 <= S.length <= 200</span>`
2.  `<span style="display: inline;">1 <= T.length <= 200</span>`
3.  <span style="display: inline;">`S` and `T` only contain lowercase letters and `'#'` characters.</span>

**Follow up:**

*   Can you solve it in `O(N)` time and `O(1)` space?


#### Solution

Language: **Python**

```python
class Solution(object):
    def backspaceCompare(self, S, T):
        """
        :type S: str
        :type T: str
        :rtype: bool
        """
        s = []
        t = []
        for i in S:
            if i == '#':
                if s:
                    s.pop()
            else:
                s.append(i)
        for i in T:
            if i == '#':
                if t:
                    t.pop()
            else:
                t.append(i)
                
        return s == t        
```
#### Notes
- time complexity: O(m+n)