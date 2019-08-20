---
layout: post
title: '1010. Pairs of Songs With Total Durations Divisible by 60'
subtitle: ''
date: 2019-08-20
categories: Leetcode
tags: Leetcode Array
---
### [1010\. Pairs of Songs With Total Durations Divisible by 60](https://leetcode.com/problems/pairs-of-songs-with-total-durations-divisible-by-60/)

Difficulty: **Easy**

Topics: **Array**


In a list of songs, the `i`-th song has a duration of `time[i]` seconds. 

Return the number of pairs of songs for which their total duration in seconds is divisible by `60`.  Formally, we want the number of indices `i < j` with `(time[i] + time[j]) % 60 == 0`.

**Example 1:**

```
Input: [30,20,150,100,40]
Output: 3
Explanation: Three pairs have a total duration divisible by 60:
(time[0] = 30, time[2] = 150): total duration 180
(time[1] = 20, time[3] = 100): total duration 120
(time[1] = 20, time[4] = 40): total duration 60
```


**Example 2:**

```
Input: [60,60,60]
Output: 3
Explanation: All three pairs have a total duration of 120, which is divisible by 60.
```


**Note:**

1.  `1 <= time.length <= 60000`
2.  `1 <= time[i] <= 500`


#### Solution

Language: **Python**

```python
class Solution(object):
    def numPairsDivisibleBy60(self, time):
        """
        :type time: List[int]
        :rtype: int
        """
        T = collections.Counter([i % 60 for i in time])
        return sum([T[i]*T[60-i] for i in range(1,30)])+(T[0]*(T[0]-1)+T[30]*(T[30]-1))//2
```

#### Notes
- count modulo of 60 and sum up pairs of time.