---
layout: post
title: '849. Maximize Distance to Closest Person'
subtitle: ''
date: 2019-08-22
categories: Leetcode
tags: Leetcode Array
---
### [849\. Maximize Distance to Closest Person](https://leetcode.com/problems/maximize-distance-to-closest-person/)

Difficulty: **Easy**

Topics: **Array**


In a row of `seats`, `1` represents a person sitting in that seat, and `0` represents that the seat is empty. 

There is at least one empty seat, and at least one person sitting.

Alex wants to sit in the seat such that the distance between him and the closest person to him is maximized. 

Return that maximum distance to closest person.


**Example 1:**

```
Input: [1,0,0,0,1,0,1]
Output: 2
Explanation: 
If Alex sits in the second open seat (seats[2]), then the closest person has distance 2.
If Alex sits in any other open seat, the closest person has distance 1.
Thus, the maximum distance to the closest person is 2.
```


**Example 2:**

```
Input: [1,0,0,0]
Output: 3
Explanation: 
If Alex sits in the last seat, the closest person is 3 seats away.
This is the maximum distance possible, so the answer is 3.
```

**Note:**

1.  `1 <= seats.length <= 20000`
2.  `seats` contains only 0s or 1s, at least one `0`, and at least one `1`.


#### Solution

Language: **Python**

```python
class Solution(object):
    def maxDistToClosest(self, seats):
        """
        :type seats: List[int]
        :rtype: int
        """
        left, cnt, ans = -1, 0, 1
        
        for i, n in enumerate(seats):
            if n == 0:
                cnt += 1
            else:
                if left < 0:
                    dist = cnt
                else:
                    dist = cnt//2 + cnt%2
                left = i
                cnt = 0
                ans = max(ans,dist)
        return max(ans,cnt)
                
```

#### Notes
- one pass
- left index starts from -1
- cnt track the length of continuous zeros
- even length zeros' distance is 1 less than odd length zeros' distance, so we use `cnt//2+cnt%2`
- the length of continuous zeros to the end of list maybe larger, so needed to be considered (`max(ans, cnt)`).