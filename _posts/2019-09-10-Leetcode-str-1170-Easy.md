---
layout: post
title: '1170. Compare Strings by Frequency of the Smallest Character'
subtitle: ''
date: 2019-09-10
categories: Leetcode
tags: Leetcode Strings
---
### [1170\. Compare Strings by Frequency of the Smallest Character](https://leetcode.com/problems/compare-strings-by-frequency-of-the-smallest-character/)

Difficulty: **Easy**

Topics: **Strings**


Let's define a function `f(s)` over a non-empty string `s`, which calculates the frequency of the smallest character in `s`. For example, if `s = "dcce"` then `f(s) = 2` because the smallest character is `"c"` and its frequency is 2.

Now, given string arrays `queries` and `words`, return an integer array `answer`, where each `answer[i]` is the number of words such that `f(queries[i])` < `f(W)`, where `W` is a word in `words`.

**Example 1:**

```
Input: queries = ["cbd"], words = ["zaaaz"]
Output: [1]
Explanation: On the first query we have f("cbd") = 1, f("zaaaz") = 3 so f("cbd") < f("zaaaz").
```

**Example 2:**

```
Input: queries = ["bbb","cc"], words = ["a","aa","aaa","aaaa"]
Output: [1,2]
Explanation: On the first query only f("bbb") < f("aaaa"). On the second query both f("aaa") and f("aaaa") are both > f("cc").
```

**Constraints:**

*   `1 <= queries.length <= 2000`
*   `1 <= words.length <= 2000`
*   `1 <= queries[i].length, words[i].length <= 10`
*   `queries[i][j]`, `words[i][j]` are English lowercase letters.


#### Solution

Language: **Python**

```python
class Solution(object):
    def numSmallerByFrequency(self, queries, words):
        """
        :type queries: List[str]
        :type words: List[str]
        :rtype: List[int]
        """
        cnt = collections.Counter(map(lambda x: x.count(min(x)),words))
        ans = []
        for q in queries:
            ans.append(sum(c for i,c in cnt.items() if q.count(min(q)) < i))
        return ans
```

#### Notes
- time complexity: O(m*n)