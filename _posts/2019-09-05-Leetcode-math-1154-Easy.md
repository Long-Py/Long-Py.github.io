---
layout: post
title: '1154. Day of the Year'
subtitle: ''
date: 2019-09-05
categories: Leetcode
tags: Leetcode Math
---
### [1154\. Day of the Year](https://leetcode.com/problems/day-of-the-year/)

Difficulty: **Easy**

Topics: **Math**

Given a string `date` representing a date formatted as `YYYY-MM-DD`, return the day number of the year.

**Example 1:**

```
Input: date = "2019-01-09"
Output: 9
Explanation: Given date is the 9th day of the year in 2019.
```

**Example 2:**

```
Input: date = "2019-02-10"
Output: 41
```

**Example 3:**

```
Input: date = "2003-03-01"
Output: 60
```

**Example 4:**

```
Input: date = "2004-03-01"
Output: 61
```

**Constraints:**

*   `date.length == 10`
*   `date[4] == date[7] == '-'`, and all other `date[i]`'s are digits
*   `date` represents a calendar date between Jan 1st, 1900 and Dec 31, 2019.


#### Solution

Language: **Python**

```python
class Solution(object):
    def dayOfYear(self, date):
        """
        :type date: str
        :rtype: int
        """
        M = [0,31,28,31,30,31,30,31,31,30,31,30,31]
        year, month, day = map(int, date.split('-'))
        is_leap_year = ((year % 400 == 0) or ((year % 4 == 0 ) and (year % 100 != 0)))
        count = day
        # Count down months, i.e. April: 3 -> 2 -> 1
        for i in range(month-1, 0, -1):
            count += M[i]
            # Add additional day for February in leap year
            if i == 2 and is_leap_year: 
                count += 1
        return count
```

#### Notes
- leap year