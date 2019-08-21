---
layout: post
title: '27. Remove Element'
subtitle: ''
date: 2019-08-20
categories: Leetcode
tags: Leetcode Array
---
### [27\. Remove Element](https://leetcode.com/problems/remove-element/)

Difficulty: **Easy**

Topics: **Array**

Given an array _nums_ and a value _val_, remove all instances of that value and return the new length.

Do not allocate extra space for another array, you must do this by **modifying the input array** with O(1) extra memory.

The order of elements can be changed. It doesn't matter what you leave beyond the new length.

**Example 1:**

```
Given nums = [3,2,2,3], val = 3,

Your function should return length = 2, with the first two elements of nums being 2.

It doesn't matter what you leave beyond the returned length.
```

**Example 2:**

```
Given nums = [0,1,2,2,3,0,4,2], val = 2,

Your function should return length = 5, with the first five elements of nums containing 0, 1, 3, 0, and 4.

Note that the order of those five elements can be arbitrary.

It doesn't matter what values are set beyond the returned length.
```

**Clarification:**

Confused why the returned value is an integer but your answer is an array?

Note that the input array is passed in by **reference**, which means modification to the input array will be known to the caller as well.

Internally you can think of this:

```
// nums is passed in by reference. (i.e., without making a copy)
int len = removeElement(nums, val);

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
    def removeElement(self, nums, val):
        """
        :type nums: List[int]
        :type val: int
        :rtype: int
        """
        l, r = 0, len(nums)-1
        while l <= r:
            if nums[r] != val:
                if nums[l] != val:
                    l += 1
                else:
                    nums[l], nums[r] = nums[r], nums[l]
                    l += 1
                    r -= 1
            else:
                r -= 1
        return l
```
#### Notes
- two pointers: move all elements that do not equal to val to the left of the list, then return the left pointer.