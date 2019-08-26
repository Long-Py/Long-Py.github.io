---
layout: post
title: '500. Keyboard Row'
subtitle: ''
date: 2019-08-26
categories: Leetcode
tags: Leetcode Strings HashTable
---
### [500\. Keyboard Row](https://leetcode.com/problems/keyboard-row/)

Difficulty: **Easy**

Topics: **HashTable**


Given a List of words, return the words that can be typed using letters of **alphabet** on only one row's of American keyboard like the image below.

![](https://assets.leetcode.com/uploads/2018/10/12/keyboard.png)

**Example:**

```
Input: ["Hello", "Alaska", "Dad", "Peace"]
Output: ["Alaska", "Dad"]
```

**Note:**

1.  You may use one character in the keyboard more than once.
2.  You may assume the input string will only contain letters of alphabet.


#### Solution

Language: **Python**

```python
class Solution(object):
    def findWords(self, words):
        """
        :type words: List[str]
        :rtype: List[str]
        """
        a=set('qwertyuiop')
        b=set('asdfghjkl')
        c=set('zxcvbnm')
        ans=[]
        for word in words:
            t=set(word.lower())
            if a&t==t:
                ans.append(word)
            if b&t==t:
                ans.append(word)
            if c&t==t:
                ans.append(word)
        return ans
```
#### Notes
- set operations: 

    ```python
    A = {0, 2, 4, 6, 8}; 
    B = {1, 2, 3, 4, 5}; 
    
    # union 
    print("Union :", A | B) 
    
    # intersection 
    print("Intersection :", A & B) 
    
    # difference 
    print("Difference :", A - B) 
    
    # symmetric difference 
    print("Symmetric difference :", A ^ B) 


    Output:
    
    ('Union :', set([0, 1, 2, 3, 4, 5, 6, 8]))
    ('Intersection :', set([2, 4]))
    ('Difference :', set([8, 0, 6]))
    ('Symmetric difference :', set([0, 1, 3, 5, 6, 8]))
    ```