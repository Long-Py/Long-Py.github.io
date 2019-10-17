---
layout: post
title: '1046. Last Stone Weight'
subtitle: ''
date: 2019-10-15
categories: Leetcode
tags: Leetcode Heap Greedy
---
### [1046\. Last Stone Weight](https://leetcode.com/problems/last-stone-weight/)

Difficulty: **Easy**

Topics: **Heap**


We have a collection of rocks, each rock has a positive integer weight.

Each turn, we choose the two **heaviest** rocks and smash them together.  Suppose the stones have weights `x` and `y` with `x <= y`.  The result of this smash is:

*   If `x == y`, both stones are totally destroyed;
*   If `x != y`, the stone of weight `x` is totally destroyed, and the stone of weight `y` has new weight `y-x`.

At the end, there is at most 1 stone left.  Return the weight of this stone (or 0 if there are no stones left.)

**Example 1:**

```
Input: [2,7,4,1,8,1]
Output: 1
Explanation: 
We combine 7 and 8 to get 1 so the array converts to [2,4,1,1,1] then,
we combine 2 and 4 to get 2 so the array converts to [2,1,1,1] then,
we combine 2 and 1 to get 1 so the array converts to [1,1,1] then,
we combine 1 and 1 to get 0 so the array converts to [1] then that's the value of last stone.
```

**Note:**

1.  `1 <= stones.length <= 30`
2.  `1 <= stones[i] <= 1000`


#### Solution

Language: **Python**

```python
class Solution(object):
    def lastStoneWeight(self, stones):
        """
        :type stones: List[int]
        :rtype: int
        """
        pq = [-i for i in stones]
        heapq.heapify(pq)
        for _ in range(len(pq)-1):
            heapq.heappush(pq,heapq.heappop(pq)-heapq.heappop(pq))
        return -pq[0]
```

#### Notes
- `heapq` is **not** max-heap. So, we have to invert sign of all values in stones.