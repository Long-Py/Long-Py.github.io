---
layout: post
title: '874. Walking Robot Simulation'
subtitle: ''
date: 2019-10-21
categories: Leetcode
tags: Leetcode Greedy Array
---
### [874\. Walking Robot Simulation](https://leetcode.com/problems/walking-robot-simulation/)

Difficulty: **Easy**

Topics: **Greedy**


A robot on an infinite grid starts at point (0, 0) and faces north.  The robot can receive one of three possible types of commands:

*   `-2`: turn left 90 degrees
*   `-1`: turn right 90 degrees
*   `1 <= x <= 9`: move forward `x` units

Some of the grid squares are obstacles. 

The `i`-th obstacle is at grid point `(obstacles[i][0], obstacles[i][1])`

If the robot would try to move onto them, the robot stays on the previous grid square instead (but still continues following the rest of the route.)

Return the **square** of the maximum Euclidean distance that the robot will be from the origin.

**Example 1:**

```
Input: commands = [4,-1,3], obstacles = []
Output: 25
Explanation: robot will go to (3, 4)
```


**Example 2:**

```
Input: commands = [4,-1,4,-2,4], obstacles = [[2,4]]
Output: 65
Explanation: robot will be stuck at (1, 4) before turning left and going to (1, 8)
```


**Note:**

1.  `0 <= commands.length <= 10000`
2.  `0 <= obstacles.length <= 10000`
3.  `-30000 <= obstacle[i][0] <= 30000`
4.  `-30000 <= obstacle[i][1] <= 30000`
5.  The answer is guaranteed to be less than `2 ^ 31`.


#### Solution

Language: **Python**

```python
class Solution(object):
    def robotSim(self, commands, obstacles):
        """
        :type commands: List[int]
        :type obstacles: List[List[int]]
        :rtype: int
        """
        x = y = 0
        ans = 0
        d = 0
        move, obstacles = [(0, 1), (-1, 0), (0, -1), (1, 0)], set(map(tuple, obstacles))
        for command in commands:
            if command == -2: d = (d + 1) % 4
            elif command == -1: d = (d - 1) % 4
            else:
                i, j = move[d]
                while command and (x + i, y + j) not in obstacles:
                    x += i
                    y += j
                    command -= 1
            ans = max(ans, x ** 2 + y ** 2)
        return ans   
```