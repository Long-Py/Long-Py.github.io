---
layout: post
title: '14. Longest Common Prefix'
subtitle: ''
date: 2019-08-23
categories: Leetcode
tags: Leetcode Array
---
### [14\. Longest Common Prefix](https://leetcode.com/problems/longest-common-prefix/)

Difficulty: **Easy**

Topics: **Array**


Write a function to find the longest common prefix string amongst an array of strings.

If there is no common prefix, return an empty string `""`.

**Example 1:**

```
Input: ["flower","flow","flight"]
Output: "fl"
```

**Example 2:**

```
Input: ["dog","racecar","car"]
Output: ""
Explanation: There is no common prefix among the input strings.
```

**Note:**

All given inputs are in lowercase letters `a-z`.


#### Solution

Language: **Python**

```python
class Solution(object):
    def longestCommonPrefix(self, strs):
        """
        :type strs: List[str]
        :rtype: str
        """
        if not strs: return ''
        w = min(strs,key=len)
        for i, c in enumerate(w):
            for word in strs:
                if word[i] != c:
                    return w[:i]
        return w
```

#### Notes
- get the smallest length word 
- time complexity: O(len(word)*len(array))