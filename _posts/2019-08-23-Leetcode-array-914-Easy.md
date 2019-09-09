---
layout: post
title: '914. X of a Kind in a Deck of Cards'
subtitle: ''
date: 2019-08-23
categories: Leetcode
tags: Leetcode Array Math
---
### [914\. X of a Kind in a Deck of Cards](https://leetcode.com/problems/x-of-a-kind-in-a-deck-of-cards/)

Difficulty: **Easy**

Topics: **Array**


In a deck of cards, each card has an integer written on it.

Return `true` if and only if you can choose `X >= 2` such that it is possible to split the entire deck into 1 or more groups of cards, where:

*   Each group has exactly `X` cards.
*   All the cards in each group have the same integer.

**Example 1:**

```
Input: [1,2,3,4,4,3,2,1]
Output: true
Explanation: Possible partition [1,1],[2,2],[3,3],[4,4]
```


**Example 2:**

```
Input: [1,1,1,2,2,2,3,3]
Output: false
Explanation: No possible partition.
```


**Example 3:**

```
Input: [1]
Output: false
Explanation: No possible partition.
```


**Example 4:**

```
Input: [1,1]
Output: true
Explanation: Possible partition [1,1]
```


**Example 5:**

```
Input: [1,1,2,2,2,2]
Output: true
Explanation: Possible partition [1,1],[2,2],[2,2]
```


**Note:**

1.  `1 <= deck.length <= 10000`
2.  `0 <= deck[i] < 10000`


#### Solution

Language: **Python**

```python
class Solution(object):
    def hasGroupsSizeX(self, deck):
        """
        :type deck: List[int]
        :rtype: bool
        """
        def gcd(a, b):
            while b: a, b = b, a % b
            return a
        count = collections.Counter(deck).values()
        return reduce(gcd, count) > 1
        
        
```

#### Notes
- **GCD** *greatest common divisor*
- `reduce()`: The reduce(fun,seq) function is used to apply a particular function passed in its argument to all of the list elements mentioned in the sequence passed along.This function is defined in “functools” module.
  
  Working : 

    - At first step, first two elements of sequence are picked and the result is obtained.
    - Next step is to apply the same function to the previously attained result and the number just succeeding the second element and the result is again stored.
    This process continues till no more elements are left in the container.
    - The final returned result is returned and printed on console.