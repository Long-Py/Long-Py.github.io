---
layout: post
title: '1221. Split a String in Balanced Strings'
subtitle: ''
date: 2019-10-16
categories: Leetcode
tags: Leetcode Greedy Strings
---
### [1221\. Split a String in Balanced Strings](https://leetcode.com/problems/split-a-string-in-balanced-strings/)

Difficulty: **Easy**

Topics: **Greedy**

_Balanced_ strings are those who have equal quantity of 'L' and 'R' characters.

Given a balanced string `s` split it in the maximum amount of balanced strings.

Return the maximum amount of splitted balanced strings.

**Example 1:**

```
Input: s = "RLRRLLRLRL"
Output: 4
Explanation: s can be split into "RL", "RRLL", "RL", "RL", each substring contains same number of 'L' and 'R'.
```

**Example 2:**

```
Input: s = "RLLLLRRRLR"
Output: 3
Explanation: s can be split into "RL", "LLLRRR", "LR", each substring contains same number of 'L' and 'R'.
```

**Example 3:**

```
Input: s = "LLLLRRRR"
Output: 1
Explanation: s can be split into "LLLLRRRR".
```

**Constraints:**

*   `1 <= s.length <= 1000`
*   `s[i] = 'L' or 'R'`


#### Solution

Language: **Python**

```python
class Solution(object):
    def balancedStringSplit(self, s):
        """
        :type s: str
        :rtype: int
        """
        if not s: return 0
        ans = 0
        cnt = 0
        for c in s:
            if c == 'R':
                cnt += 1
            else:
                cnt -= 1
            if cnt == 0:
                ans += 1
        return ans
            
```