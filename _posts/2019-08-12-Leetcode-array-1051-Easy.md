---
layout: post
title: '1051. Height Checker'
subtitle: ''
date: 2019-08-12
categories: Leetcode
tags: Leetcode Array
---
### [1051\. Height Checker](https://leetcode.com/problems/height-checker/)

Difficulty: **Easy**

Topics: **Array**


Students are asked to stand in non-decreasing order of heights for an annual photo.

Return the minimum number of students not standing in the right positions.  (This is the number of students that must move in order for all students to be standing in non-decreasing order of height.)

**Example 1:**

```
Input: [1,1,4,2,1,3]
Output: 3
Explanation: 
Students with heights 4, 3 and the last 1 are not standing in the right positions.
```

**Note:**

1.  `1 <= heights.length <= 100`
2.  `1 <= heights[i] <= 100`


#### Solution

Language: **Python**

```python
class Solution(object):
    def heightChecker(self, heights):
        """
        :type heights: List[int]
        :rtype: int
        """
        return sum(h1 != h2 for h1, h2 in zip(heights, sorted(heights)))
```

#### Notes
- **hint**: Build the correct order of heights by sorting another array, then compare the two arrays.
- The `zip()` function returns a zip object, which is an iterator of **tuples** where the first item in each passed iterator is paired together, and then the second item in each passed iterator are paired together etc.
If the passed iterators have different lengths, the iterator with **the least** items decides the length of the new iterator.
- The `sorted()` function returns a sorted list of the specified iterable object.
You can specify ascending or descending order. Strings are sorted alphabetically, and numbers are sorted numerically.

    `sorted(iterable, key=func, reverse=reverse)`