---
layout: post
title: '409. Longest Palindrome'
subtitle: ''
date: 2019-08-28
categories: Leetcode
tags: Leetcode Strings HashTable
---
### [409\. Longest Palindrome](https://leetcode.com/problems/longest-palindrome/)

Difficulty: **Easy**

Topics: **HashTable**


Given a string which consists of lowercase or uppercase letters, find the length of the longest palindromes that can be built with those letters.

This is case sensitive, for example `"Aa"` is not considered a palindrome here.

**Note:**  
Assume the length of given string will not exceed 1,010.

**Example:**

```
Input:
"abccccdd"

Output:
7

Explanation:
One longest palindrome that can be built is "dccaccd", whose length is 7.
```


#### Solution

Language: **Python**

```python
class Solution(object):
    def longestPalindrome(self, s):
        """
        :type s: str
        :rtype: int
        """
        
        ans = 0
        for v in collections.Counter(s).values():
            ans += v / 2 * 2
            if ans % 2 == 0 and v % 2 == 1:
                ans += 1
        return ans
```

#### Notes
- notice: `ans += v / 2 * 2` ---> `5//2*2 == 4`