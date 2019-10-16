---
layout: post
title: '703. Kth Largest Element in a Stream'
subtitle: ''
date: 2019-10-16
categories: Leetcode
tags: Leetcode Heap
---
### [703\. Kth Largest Element in a Stream](https://leetcode.com/problems/kth-largest-element-in-a-stream/)

Difficulty: **Easy**

Topics: **Heap**


Design a class to find the **k**th largest element in a stream. Note that it is the kth largest element in the sorted order, not the kth distinct element.

Your `KthLargest` class will have a constructor which accepts an integer `k` and an integer array `nums`, which contains initial elements from the stream. For each call to the method `KthLargest.add`, return the element representing the kth largest element in the stream.

**Example:**

```
int k = 3;
int[] arr = [4,5,8,2];
KthLargest kthLargest = new KthLargest(3, arr);
kthLargest.add(3);   // returns 4
kthLargest.add(5);   // returns 5
kthLargest.add(10);  // returns 5
kthLargest.add(9);   // returns 8
kthLargest.add(4);   // returns 8
```

**Note:**  
You may assume that `nums`' length ≥ `k-1` and `k` ≥ 1.


#### Solution

Language: **Python**

```python
class KthLargest(object):
​
    def __init__(self, k, nums):
        self.pool = nums
        self.k = k
        heapq.heapify(self.pool)
        while len(self.pool) > k:
            heapq.heappop(self.pool)
​
            
    def add(self, val):
        if len(self.pool) < self.k:
            heapq.heappush(self.pool, val)
        elif val > self.pool[0]:
            heapq.heapreplace(self.pool, val)
        return self.pool[0]
        
                
        
​
# Your KthLargest object will be instantiated and called as such:
# obj = KthLargest(k, nums)
# param_1 = obj.add(val)
```

#### Notes
- [Heap queue (or heapq) in Python](https://www.geeksforgeeks.org/heap-queue-or-heapq-in-python/)