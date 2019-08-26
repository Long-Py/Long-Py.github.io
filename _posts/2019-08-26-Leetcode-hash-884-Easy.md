---
layout: post
title: '884. Uncommon Words from Two Sentences'
subtitle: ''
date: 2019-08-26
categories: Leetcode
tags: Leetcode Array HashTable
---

### [884\. Uncommon Words from Two Sentences](https://leetcode.com/problems/uncommon-words-from-two-sentences/)

Difficulty: **Easy**

Topics: **HashTable**


We are given two sentences `A` and `B`.  (A _sentence_ is a string of space separated words.  Each _word_ consists only of lowercase letters.)

A word is _uncommon_ if it appears exactly once in one of the sentences, and does not appear in the other sentence.

Return a list of all uncommon words. 

You may return the list in any order.


**Example 1:**

```
Input: A = "this apple is sweet", B = "this apple is sour"
Output: ["sweet","sour"]
```


**Example 2:**

```
Input: A = "apple apple", B = "banana"
Output: ["banana"]
```

**Note:**

1.  `0 <= A.length <= 200`
2.  `0 <= B.length <= 200`
3.  `A` and `B` both contain only spaces and lowercase letters.


#### Solution

Language: **Python**

```python
class Solution(object):
    def uncommonFromSentences(self, A, B):
        """
        :type A: str
        :type B: str
        :rtype: List[str]
        """
        l = A.split() + B.split()
        ans = []
        for w, c in collections.Counter(l).items():
            if c == 1:
                ans.append(w)
        return ans
```