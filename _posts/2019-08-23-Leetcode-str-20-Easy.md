---
layout: post
title: '20. Valid Parentheses'
subtitle: ''
date: 2019-08-23
categories: Leetcode
tags: Leetcode Strings
---
### [20\. Valid Parentheses](https://leetcode.com/problems/valid-parentheses/)

Difficulty: **Easy**

Topics: **Strings**


Given a string containing just the characters `'('`, `')'`, `'{'`, `'}'`, `'['` and `']'`, determine if the input string is valid.

An input string is valid if:

1.  Open brackets must be closed by the same type of brackets.
2.  Open brackets must be closed in the correct order.

Note that an empty string is also considered valid.

**Example 1:**

```
Input: "()"
Output: true
```

**Example 2:**

```
Input: "()[]{}"
Output: true
```

**Example 3:**

```
Input: "(]"
Output: false
```

**Example 4:**

```
Input: "([)]"
Output: false
```

**Example 5:**

```
Input: "{[]}"
Output: true
```


#### Solution

Language: **Python**

```python
class Solution(object):
    def isValid(self, s):
        """
        :type s: str
        :rtype: bool
        """
        stack = []
        for c in s:
            if stack and c == ')' and stack[-1] == '(':
                stack.pop()
            elif stack and c == ']' and stack[-1] == '[':
                stack.pop()
            elif stack and c == '}' and stack[-1] == '{':      
                stack.pop()
            else:
                stack.append(c)
        return not stack
```

#### Notes
- apply **stack** using list