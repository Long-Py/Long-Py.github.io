---
layout: post
title: '942. DI String Match'
subtitle: ''
date: 2019-09-03
categories: Leetcode
tags: Leetcode Math Array Strings
---
### [942\. DI String Match](https://leetcode.com/problems/di-string-match/)

Difficulty: **Easy**

Topics: **Math**


Given a string `S` that **only** contains "I" (increase) or "D" (decrease), let `N = S.length`.

Return **any** permutation `A` of `[0, 1, ..., N]` such that for all `i = 0, ..., N-1`:

*   If `S[i] == "I"`, then `A[i] < A[i+1]`
*   If `S[i] == "D"`, then `A[i] > A[i+1]`

**Example 1:**

```
Input: "IDID"
Output: [0,4,1,3,2]
```


**Example 2:**

```
Input: "III"
Output: [0,1,2,3]
```


**Example 3:**

```
Input: "DDI"
Output: [3,2,0,1]
```


**Note:**

1.  `1 <= S.length <= 10000`
2.  `S` only contains characters `"I"` or `"D"`.


#### Solution

Language: **Python**

```python
class Solution(object):
    def diStringMatch(self, S):
        """
        :type S: str
        :rtype: List[int]
        """
        l, r = 0, len(S)
        ans = []
        for c in S:
            if c == 'I':
                ans.append(l)
                l += 1
            else:
                ans.append(r)
                r -= 1
        return ans + [r] ### same as `ans + [l]`
```

#### Notes
- Do not forget add `l == r`