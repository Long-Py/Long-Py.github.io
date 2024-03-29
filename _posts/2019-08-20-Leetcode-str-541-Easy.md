---
layout: post
title: '541. Reverse String II'
subtitle: ''
date: 2019-08-20
categories: Leetcode
tags: Leetcode Strings
---
### [541\. Reverse String II](https://leetcode.com/problems/reverse-string-ii/)

Difficulty: **Easy**

Topics: **Strings**

Given a string and an integer k, you need to reverse the first k characters for every 2k characters counting from the start of the string. If there are less than k characters left, reverse all of them. If there are less than 2k but greater than or equal to k characters, then reverse the first k characters and left the other as original.

**Example:**  

```
Input: s = "abcdefg", k = 2
Output: "bacdfeg"
```

**Restrictions:**

1.  The string consists of lower English letters only.
2.  Length of the given string and k will in the range [1, 10000]


#### Solution

Language: **Python**

```python
class Solution(object):
    def reverseStr(self, s, k):
        """
        :type s: str
        :type k: int
        :rtype: str
        """
        s = list(s)
        for i in range(0,len(s),2*k):
            if i+k<len(s):
                s[i:i+k] = s[i:i+k][::-1]
            else:
                s[i:] = s[i:][::-1]
        return ''.join(s)
```

#### Notes
- reverse str every 2*k step
- *if statement* to justify the rest length is k or less.