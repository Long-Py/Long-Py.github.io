---
layout: post
title: '830. Positions of Large Groups'
subtitle: ''
date: 2019-08-20
categories: Leetcode
tags: Leetcode Array
---
### [830\. Positions of Large Groups](https://leetcode.com/problems/positions-of-large-groups/)

Difficulty: **Easy**

Topics: **Array**


In a string `S` of lowercase letters, these letters form consecutive groups of the same character.

For example, a string like `S = "abbxxxxzyy"` has the groups `"a"`, `"bb"`, `"xxxx"`, `"z"` and `"yy"`.

Call a group _large_ if it has 3 or more characters.  We would like the starting and ending positions of every large group.

The final answer should be in lexicographic order.

**Example 1:**

```
Input: "abbxxxxzzy"
Output: [[3,6]]
Explanation: "xxxx" is the single large group with starting  3 and ending positions 6.
```

**Example 2:**

```
Input: "abc"
Output: []
Explanation: We have "a","b" and "c" but no large group.
```

**Example 3:**

```
Input: "abcdddeeeeaabbbcd"
Output: [[3,5],[6,9],[12,14]]
```

**Note: ** `1 <= S.length <= 1000`


#### Solution

Language: **Python**

```python
class Solution(object):
    def largeGroupPositions(self, S):
        """
        :type S: str
        :rtype: List[List[int]]
        """
        idx = 0
        ans = []
        for i in range(len(S)):
            if i == len(S)-1 or S[i] != S[i+1]:
                if i+1-idx >= 3:
                    ans.append([idx,i])
                idx = i+1
        return ans
```

#### Notes
- two pointers: idx represent the start of a group
- `i == len(S)-1` before `S[i] != S[i+1]`, or will raise error: **index out of range**