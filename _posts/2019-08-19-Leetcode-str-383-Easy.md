---
layout: post
title: '383. Ransom Note'
subtitle: ''
date: 2019-08-19
categories: Leetcode
tags: Leetcode Strings
---
### [383\. Ransom Note](https://leetcode.com/problems/ransom-note/)

Difficulty: **Easy**

Topics: **Strings**


Given an arbitrary ransom note string and another string containing letters from all the magazines, write a function that will return true if the ransom note can be constructed from the magazines ; otherwise, it will return false.

Each letter in the magazine string can only be used once in your ransom note.

**Note:**  
You may assume that both strings contain only **lowercase** letters.

```
canConstruct("a", "b") -> false
canConstruct("aa", "ab") -> false
canConstruct("aa", "aab") -> true
```


#### Solution

Language: **Python**

```python
class Solution(object):
    def canConstruct(self, ransomNote, magazine):
        """
        :type ransomNote: str
        :type magazine: str
        :rtype: bool
        """
        cnt = [0]*26
        for c in magazine:
            cnt[ord(c)-ord('a')] += 1
        
        for c in ransomNote:
            cnt[ord(c)-ord('a')] -= 1
            if cnt[ord(c)-ord('a')] < 0:
                return False
        return True
```

#### Notes
- two passes
  - 1st pass: create a list of 26 letters with counts by magazine list
  - 2nd pass: subtract count of letters in ransomNote, when we get a negative count we return False.
- time complexity: O(n), space complexity: O(1)
