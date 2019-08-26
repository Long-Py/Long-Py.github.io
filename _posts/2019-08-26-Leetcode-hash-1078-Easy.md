---
layout: post
title: '1078. Occurrences After Bigram'
subtitle: ''
date: 2019-08-26
categories: Leetcode
tags: Leetcode Strings HashTable
---
### [1078\. Occurrences After Bigram](https://leetcode.com/problems/occurrences-after-bigram/)

Difficulty: **Easy**

Topics: **HashTable**


Given words `first` and `second`, consider occurrences in some `text` of the form "`first second third`", where `second` comes immediately after `first`, and `third` comes immediately after `second`.

For each such occurrence, add "`third`" to the answer, and return the answer.

**Example 1:**

```
Input: text = "alice is a good girl she is a good student", first = "a", second = "good"
Output: ["girl","student"]
```


**Example 2:**

```
Input: text = "we will we will rock you", first = "we", second = "will"
Output: ["we","rock"]
```

**Note:**

1.  `1 <= text.length <= 1000`
2.  `text` consists of space separated words, where each word consists of lowercase English letters.
3.  `1 <= first.length, second.length <= 10`
4.  `first` and `second` consist of lowercase English letters.


#### Solution

Language: **Python**

```python
class Solution(object):
    def findOcurrences(self, text, first, second):
        """
        :type text: str
        :type first: str
        :type second: str
        :rtype: List[str]
        """
        ans = []
        text = text.split()
        for i in range(1, len(text)-1):
            if text[i-1] == first and text[i] == second:
                ans.append(text[i+1])
        return ans
```