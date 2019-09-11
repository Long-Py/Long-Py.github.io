---
layout: post
title: '744. Find Smallest Letter Greater Than Target'
subtitle: ''
date: 2019-09-11
categories: Leetcode
tags: Leetcode BinarySearch
---
### [744\. Find Smallest Letter Greater Than Target](https://leetcode.com/problems/find-smallest-letter-greater-than-target/)

Difficulty: **Easy**

Topics: **Binary Search**


Given a list of sorted characters `letters` containing only lowercase letters, and given a target letter `target`, find the smallest element in the list that is larger than the given target.

Letters also wrap around. For example, if the target is `target = 'z'` and `letters = ['a', 'b']`, the answer is `'a'`.

**Examples:**  

```
Input:
letters = ["c", "f", "j"]
target = "a"
Output: "c"

Input:
letters = ["c", "f", "j"]
target = "c"
Output: "f"

Input:
letters = ["c", "f", "j"]
target = "d"
Output: "f"

Input:
letters = ["c", "f", "j"]
target = "g"
Output: "j"

Input:
letters = ["c", "f", "j"]
target = "j"
Output: "c"

Input:
letters = ["c", "f", "j"]
target = "k"
Output: "c"
```

**Note:**  

1.  `letters` has a length in range `[2, 10000]`.
2.  `letters` consists of lowercase letters, and contains at least 2 unique letters.
3.  `target` is a lowercase letter.


#### Solution

Language: **Python**

```python
class Solution(object):
    def nextGreatestLetter(self, letters, target):
        """
        :type letters: List[str]
        :type target: str
        :rtype: str
        """
        l, r = 0, len(letters)-1
        if target < letters[0] or target >= letters[-1]: return letters[0] 
        while l <= r:
            mid = l +(r-l)//2
            if letters[mid] <= target:
                l = mid + 1
            else:
                r = mid - 1
        return letters[l]
```

#### Notes
- be careful of edge cases