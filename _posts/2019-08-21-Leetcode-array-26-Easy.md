---
layout: post
title: '26. Remove Duplicates from Sorted Array'
subtitle: ''
date: 2019-08-21
categories: Leetcode
tags: Leetcode Array TwoPointers
---
### [26\. Remove Duplicates from Sorted Array](https://leetcode.com/problems/remove-duplicates-from-sorted-array/)

Difficulty: **Easy**

Topics: **Array**

Given a sorted array _nums_, remove the duplicates such that each element appear only _once_ and return the new length.

Do not allocate extra space for another array, you must do this by **modifying the input array** with O(1) extra memory.

**Example 1:**

```
Given nums = [1,1,2],

Your function should return length = 2, with the first two elements of nums being 1 and 2 respectively.

It doesn't matter what you leave beyond the returned length.
```

**Example 2:**

```
Given nums = [0,0,1,1,1,2,2,3,3,4],

Your function should return length = 5, with the first five elements of nums being modified to 0, 1, 2, 3, and 4 respectively.

It doesn't matter what values are set beyond the returned length.
```

**Clarification:**

Confused why the returned value is an integer but your answer is an array?

Note that the input array is passed in by **reference**, which means modification to the input array will be known to the caller as well.

Internally you can think of this:

```
// nums is passed in by reference. (i.e., without making a copy)
int len = removeDuplicates(nums);

// any modification to nums in your function would be known by the caller.
// using the length returned by your function, it prints the first len elements.
for (int i = 0; i < len; i++) {
    print(nums[i]);
}
```


#### Solution

Language: **Python**

```python
class Solution(object):
    def removeDuplicates(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        if not nums: return 0
        idx = 0
        for n in nums:
            if n != nums[idx]:
                idx += 1
                nums[idx] = n
        return idx+1
```

#### Notes
- two pointers
- return new length, so `idx + 1`