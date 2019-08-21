---
layout: post
title: '925. Long Pressed Name'
subtitle: ''
date: 2019-08-21
categories: Leetcode
tags: Leetcode Strings
---
### [925\. Long Pressed Name](https://leetcode.com/problems/long-pressed-name/)

Difficulty: **Easy**

Topics: **Strings**


Your friend is typing his `name` into a keyboard.  Sometimes, when typing a character `c`, the key might get _long pressed_, and the character will be typed 1 or more times.

You examine the `typed` characters of the keyboard.  Return `True` if it is possible that it was your friends name, with some characters (possibly none) being long pressed.

**Example 1:**

```
Input: name = "alex", typed = "aaleex"
Output: true
Explanation: 'a' and 'e' in 'alex' were long pressed.
```


**Example 2:**

```
Input: name = "saeed", typed = "ssaaedd"
Output: false
Explanation: 'e' must have been pressed twice, but it wasn't in the typed output.
```


**Example 3:**

```
Input: name = "leelee", typed = "lleeelee"
Output: true
```


**Example 4:**

```
Input: name = "laiden", typed = "laiden"
Output: true
Explanation: It's not necessary to long press any character.
```


**Note:**

1.  `name.length <= 1000`
2.  `typed.length <= 1000`
3.  The characters of `name` and `typed` are lowercase letters.


#### Solution

Language: **Python**

```python
class Solution(object):
    def isLongPressedName(self, name, typed):
        """
        :type name: str
        :type typed: str
        :rtype: bool
        """
        g1 = [(k, len(list(grp))) for k, grp in itertools.groupby(name)]
        g2 = [(k, len(list(grp))) for k, grp in itertools.groupby(typed)]
        return len(g1) == len(g2) and all(k1 == k2 and v1 <= v2 for (k1,v1), (k2,v2) in zip(g1, g2))        
```

#### Notes
- group strings into blocks then compare length of each blocks
- time complexity: O(N+T), N: length of name, T: length of typed