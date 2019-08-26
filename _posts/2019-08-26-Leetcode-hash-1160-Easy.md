---
layout: post
title: '1160. Find Words That Can Be Formed by Characters'
subtitle: ''
date: 2019-08-26
categories: Leetcode
tags: Leetcode Strings HashTable
---
### [1160\. Find Words That Can Be Formed by Characters](https://leetcode.com/problems/find-words-that-can-be-formed-by-characters/)

Difficulty: **Easy**

Topics: **HashTable**


You are given an array of strings `words` and a string `chars`.

A string is _good_ if it can be formed by characters from `chars` (each character can only be used once).

Return the sum of lengths of all good strings in `words`.

**Example 1:**

```
Input: words = ["cat","bt","hat","tree"], chars = "atach"
Output: 6
Explanation: 
The strings that can be formed are "cat" and "hat" so the answer is 3 + 3 = 6.
```

**Example 2:**

```
Input: words = ["hello","world","leetcode"], chars = "welldonehoneyr"
Output: 10
Explanation: 
The strings that can be formed are "hello" and "world" so the answer is 5 + 5 = 10.
```

**Note:**

1.  `1 <= words.length <= 1000`
2.  `1 <= words[i].length, chars.length <= 100`
3.  All strings contain lowercase English letters only.


#### Solution

Language: **Python**

```python
class Solution(object):
    def countCharacters(self, words, chars):
        """
        :type words: List[str]
        :type chars: str
        :rtype: int
        """
        cnt = collections.Counter(chars)
        ans = 0
        for w in words:
            tmp = collections.Counter(w)
            if all(tmp[c]<=cnt[c] for c in w):
                ans += len(w)
        return ans
```

#### Notes
- time complexity: O(N*M), N: length of chars list, M: the largest length of word in words list
