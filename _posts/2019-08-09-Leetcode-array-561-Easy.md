---
layout: post
title: '561. Array Partition I'
subtitle: ''
date: 2019-08-09
categories: Leetcode
tags: Leetcode Array
---
### [561\. Array Partition I](https://leetcode.com/problems/array-partition-i/)

Difficulty: **Easy**

Topics: **Array**


Given an array of **2n** integers, your task is to group these integers into **n** pairs of integer, say (a<sub style="display: inline;">1</sub>, b<sub style="display: inline;">1</sub>), (a<sub style="display: inline;">2</sub>, b<sub style="display: inline;">2</sub>), ..., (a<sub style="display: inline;">n</sub>, b<sub style="display: inline;">n</sub>) which makes sum of min(a<sub style="display: inline;">i</sub>, b<sub style="display: inline;">i</sub>) for all i from 1 to n as large as possible.

**Example 1:**  

```
Input: [1,4,3,2]

Output: 4
Explanation: n is 2, and the maximum sum of pairs is 4 = min(1, 2) + min(3, 4).
```

**Note:**  

1.  **n** is a positive integer, which is in the range of [1, 10000].
2.  All the integers in the array will be in the range of [-10000, 10000].


#### Solution

Language: **Python**

```python
class Solution(object):
    def arrayPairSum(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        return sum(sorted(nums)[::2])
```

#### Notes
- **Proof**: In each pair, the larger number will always be ignored (no matter the larger number is 1 more than the smaller or 1000 more than the smaller).
Hence, we want to sacrifice the larger number that is just a little bit larger than the smaller.
That's why we want to **sort** the array to find the next larger element of each element.