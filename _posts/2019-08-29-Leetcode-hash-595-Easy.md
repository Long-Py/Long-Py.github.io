---
layout: post
title: '594. Longest Harmonious Subsequence'
subtitle: ''
date: 2019-08-29
categories: Leetcode
tags: Leetcode Array HashTable
---
### [594\. Longest Harmonious Subsequence](https://leetcode.com/problems/longest-harmonious-subsequence/)

Difficulty: **Easy**

Topics: **HashTable**


We define a harmounious array as an array where the difference between its maximum value and its minimum value is **exactly** 1.

Now, given an integer array, you need to find the length of its longest harmonious subsequence among all its possible .

**Example 1:**

```
Input: [1,3,2,2,5,2,3,7]
Output: 5
Explanation: The longest harmonious subsequence is [3,2,2,2,3].
```

**Note:** The length of the input array will not exceed 20,000.


#### Solution

Language: **Python**

```python
class Solution(object):
    def findLHS(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        count = collections.Counter(nums)
        ans = 0
        for x in count:
            if x+1 in count:
                ans = max(ans, count[x] + count[x+1])
        return ans        
```

#### Notes
- time complexity: O(n)