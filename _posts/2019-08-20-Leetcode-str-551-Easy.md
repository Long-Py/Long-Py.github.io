---
layout: post
title: '551. Student Attendance Record I'
subtitle: ''
date: 2019-08-20
categories: Leetcode
tags: Leetcode Strings
---
### [551\. Student Attendance Record I](https://leetcode.com/problems/student-attendance-record-i/)

Difficulty: **Easy**

Topics: **Strings**

You are given a string representing an attendance record for a student. The record only contains the following three characters:

1.  **'A'** : Absent.
2.  **'L'** : Late.
3.  **'P'** : Present.

A student could be rewarded if his attendance record doesn't contain **more than one 'A' (absent)** or **more than two continuous 'L' (late)**.

You need to return whether the student could be rewarded according to his attendance record.

**Example 1:**  

```
Input: "PPALLP"
Output: True
```

**Example 2:**  

```
Input: "PPALLL"
Output: False
```


#### Solution

Language: **Python**

```python
class Solution(object):
    def checkRecord(self, s):
        """
        :type s: str
        :rtype: bool
        """
        return s.count('A') <= 1 and 'LLL' not in s
```

#### Notes
- count of letter A is less than 2
- 'LLL' is not a substring of s