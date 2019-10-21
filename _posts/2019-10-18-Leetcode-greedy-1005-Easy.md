---
layout: post
title: '1005. Maximize Sum Of Array After K Negations'
subtitle: ''
date: 2019-10-18
categories: Leetcode
tags: Leetcode Greedy Array
---
### [1005\. Maximize Sum Of Array After K Negations](https://leetcode.com/problems/maximize-sum-of-array-after-k-negations/)

Difficulty: **Easy**

Topics: **Greedy**

Given an array `A` of integers, we **must** modify the array in the following way: we choose an `i` and replace `A[i]` with `-A[i]`, and we repeat this process `K` times in total.  (We may choose the same index `i` multiple times.)

Return the largest possible sum of the array after modifying it in this way.

**Example 1:**

```
Input: A = [4,2,3], K = 1
Output: 5
Explanation: Choose indices (1,) and A becomes [4,-2,3].
```


**Example 2:**

```
Input: A = [3,-1,0,2], K = 3
Output: 6
Explanation: Choose indices (1, 2, 2) and A becomes [3,1,0,2].
```


**Example 3:**

```
Input: A = [2,-3,-1,5,-4], K = 2
Output: 13
Explanation: Choose indices (1, 4) and A becomes [2,3,-1,5,4].
```


**Note:**

1.  `1 <= A.length <= 10000`
2.  `1 <= K <= 10000`
3.  `-100 <= A[i] <= 100`


#### Solution

Language: **Python**

```python
class Solution(object):
    def largestSumAfterKNegations(self, A, K):
        """
        :type A: List[int]
        :type K: int
        :rtype: int
        """
        heapq.heapify(A)
        
        for _ in range(K):
            heapq.heappush(A,-1 * heapq.heappop(A))
        
        return sum(A)
```

#### Notes

- time complexity of heapq
  
  heapq is a `binary heap`, with O(log n) push and O(log n) pop. See the heapq source code.

    The algorithm you show takes O(n log n) to push all the items onto the heap, and then O((n-k) log n) to find the kth largest element. So the complexity would be O(n log n). It also requires O(n) extra space.