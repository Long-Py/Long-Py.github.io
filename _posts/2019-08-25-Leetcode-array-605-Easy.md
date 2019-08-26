---
layout: post
title: '605. Can Place Flowers'
subtitle: ''
date: 2019-08-25
categories: Leetcode
tags: Leetcode Array
---
### [605\. Can Place Flowers](https://leetcode.com/problems/can-place-flowers/)

Difficulty: **Easy**

Topics: **Array**


Suppose you have a long flowerbed in which some of the plots are planted and some are not. However, flowers cannot be planted in adjacent plots - they would compete for water and both would die.

Given a flowerbed (represented as an array containing 0 and 1, where 0 means empty and 1 means not empty), and a number **n**, return if **n** new flowers can be planted in it without violating the no-adjacent-flowers rule.

**Example 1:**  

```
Input: flowerbed = [1,0,0,0,1], n = 1
Output: True
```

**Example 2:**  

```
Input: flowerbed = [1,0,0,0,1], n = 2
Output: False
```

**Note:**  

1.  The input array won't violate no-adjacent-flowers rule.
2.  The input array size is in the range of [1, 20000].
3.  **n** is a non-negative integer which won't exceed the input array size.


#### Solution

Language: **Python**

```python
class Solution(object):
    def canPlaceFlowers(self, flowerbed, n):
        """
        :type flowerbed: List[int]
        :type n: int
        :rtype: bool
        """
        for i, x in enumerate(flowerbed):
            if not x and (i == 0 or flowerbed[i-1] == 0) and (i == len(flowerbed)-1 or flowerbed[i+1] == 0):
                n -= 1
                flowerbed[i] = 1
        return n <= 0
    
            
```
#### Notes
- one pass: will change the list.