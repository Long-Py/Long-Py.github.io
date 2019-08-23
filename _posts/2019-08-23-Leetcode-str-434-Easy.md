---
layout: post
title: '434. Number of Segments in a String'
subtitle: ''
date: 2019-08-23
categories: Leetcode
tags: Leetcode Strings
---
### [434\. Number of Segments in a String](https://leetcode.com/problems/number-of-segments-in-a-string/)

Difficulty: **Easy**

Topics: **Strings**


Count the number of segments in a string, where a segment is defined to be a contiguous sequence of non-space characters.

Please note that the string does not contain any **non-printable** characters.

**Example:**

```
Input: "Hello, my name is John"
Output: 5
```


#### Solution

Language: **Python**

```python
class Solution(object):
    def countSegments(self, s):
        """
        :type s: str
        :rtype: int
        """
        s = s.strip()
        if not s: return 0
        cnt = 0
        for i in range(len(s)):
            if (i == 0 or s[i-1] == ' ') and s[i] != ' ':
                cnt += 1
        return cnt
            
```

#### Notes
- `strip()` the space on both sides
- check `i == 0` first