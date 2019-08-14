---
layout: post
title: '824. Goat Latin'
subtitle: ''
date: 2019-08-14
categories: Leetcode
tags: Leetcode Strings
---
### [824\. Goat Latin](https://leetcode.com/problems/goat-latin/)

Difficulty: **Easy**

Topics: **Strings**


A sentence `S` is given, composed of words separated by spaces. Each word consists of lowercase and uppercase letters only.

We would like to convert the sentence to "_Goat Latin"_ (a made-up language similar to Pig Latin.)

The rules of Goat Latin are as follows:

*   If a word begins with a vowel (a, e, i, o, or u), append `"ma"` to the end of the word.  
    For example, the word 'apple' becomes 'applema'.  

*   If a word begins with a consonant (i.e. not a vowel), remove the first letter and append it to the end, then add `"ma"`.  
    For example, the word `"goat"` becomes `"oatgma"`.  

*   Add one letter `'a'` to the end of each word per its word index in the sentence, starting with 1.  
    For example, the first word gets `"a"` added to the end, the second word gets `"aa"` added to the end and so on.

Return the final sentence representing the conversion from `S` to Goat Latin. 

**Example 1:**

```
Input: "I speak Goat Latin"
Output: "Imaa peaksmaaa oatGmaaaa atinLmaaaaa"
```

**Example 2:**

```
Input: "The quick brown fox jumped over the lazy dog"
Output: "heTmaa uickqmaaa rownbmaaaa oxfmaaaaa umpedjmaaaaaa overmaaaaaaa hetmaaaaaaaa azylmaaaaaaaaa ogdmaaaaaaaaaa"
```

Notes:

*   `S` contains only uppercase, lowercase and spaces. Exactly one space between each word.
*   `1 <= S.length <= 150`.


#### Solution

Language: **Python**

```python
class Solution(object):
    def toGoatLatin(self, S):
        """
        :type S: str
        :rtype: str
        """
        d = ('a','e','i','o','u','A','E','I','O','U')
        res = ''
        for i,word in enumerate(S.split()):
            if word[0] in d:
                word += 'ma' + 'a'*(i+1)
            else:
                word = word[1:] + word[0] + 'ma' + 'a'*(i+1)
            res += word + " "
        return res.strip()
```

#### Notes
- The `strip()` method removes any **leading** (spaces at the beginning) and **trailing** (spaces at the end) characters (space is the default leading character to remove)