---
layout: post
title: '917. Reverse Only Letters'
subtitle: ''
date: 2019-08-14
categories: Leetcode
tags: Leetcode Strings
---
### [917\. Reverse Only Letters](https://leetcode.com/problems/reverse-only-letters/)

Difficulty: **Easy**

Topics: **Strings**


Given a string `S`, return the "reversed" string where all characters that are not a letter stay in the same place, and all letters reverse their positions.


**Example 1:**

```
Input: "ab-cd"
Output: "dc-ba"
```


**Example 2:**

```
Input: "a-bC-dEf-ghIj"
Output: "j-Ih-gfE-dCba"
```


**Example 3:**

```
Input: "Test1ng-Leet=code-Q!"
Output: "Qedo1ct-eeLg=ntse-T!"
```


**<span style="display: inline;">Note:</span>**

1.  `S.length <= 100`
2.  `33 <= S[i].ASCIIcode <= 122` 
3.  `S` doesn't contain `\` or `"`


#### Solution

Language: **Python**

```python
class Solution(object):
    def reverseOnlyLetters(self, S):
        """
        :type S: str
        :rtype: str
        """
        S = list(S)
        l, r = 0, len(S)-1
        while l < r:
            if not S[l].isalpha():
                l += 1
            elif not S[r].isalpha():
                r -= 1
            else:
                S[l], S[r] = S[r], S[l]
                l += 1
                r -= 1
        return ''.join(S)
```

#### Notes:
- **two points**
- transfer str to **list**, or raise an error: 
  > "unicode does not support assignment"
- The `isalpha()` method returns True if all the characters are alphabet letters (a-z).
- The `isalnum()` method returns True if all the characters are alphanumeric, meaning alphabet letter (a-z) and numbers (0-9).