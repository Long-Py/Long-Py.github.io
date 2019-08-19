---
layout: post
title: '387. First Unique Character in a String'
subtitle: ''
date: 2019-08-19
categories: Leetcode
tags: Leetcode Strings
---

### [387\. First Unique Character in a String](https://leetcode.com/problems/first-unique-character-in-a-string/)

Difficulty: **Easy**

Topics: **Strings**


Given a string, find the first non-repeating character in it and return it's index. If it doesn't exist, return -1.

**Examples:**

```
s = "leetcode"
return 0.

s = "loveleetcode",
return 2.
```

**Note:** You may assume the string contain only lowercase letters.


#### Solution

Language: **Python**

```python
class Solution(object):
    def firstUniqChar(self, s):
        """
        :type s: str
        :rtype: int
        """
        cnt = collections.Counter(s)
        for i,c in enumerate(s):
            if cnt[c] == 1:
                return i
        return -1
```

#### Notes
- two passes
  - 1st pass: get count of all letters in s
  - 2nd pass: when count == 1 return the index of that letter
