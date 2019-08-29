---
layout: post
title: '599. Minimum Index Sum of Two Lists'
subtitle: ''
date: 2019-08-28
categories: Leetcode
tags: Leetcode Array HashTable
---
### [599\. Minimum Index Sum of Two Lists](https://leetcode.com/problems/minimum-index-sum-of-two-lists/)

Difficulty: **Easy**

Topics: **HashTable**

Suppose Andy and Doris want to choose a restaurant for dinner, and they both have a list of favorite restaurants represented by strings.

You need to help them find out their **common interest** with the **least list index sum**. If there is a choice tie between answers, output all of them with no order requirement. You could assume there always exists an answer.

**Example 1:**  

```
Input:
["Shogun", "Tapioca Express", "Burger King", "KFC"]
["Piatti", "The Grill at Torrey Pines", "Hungry Hunter Steakhouse", "Shogun"]
Output: ["Shogun"]
Explanation: The only restaurant they both like is "Shogun".
```

**Example 2:**  

```
Input:
["Shogun", "Tapioca Express", "Burger King", "KFC"]
["KFC", "Shogun", "Burger King"]
Output: ["Shogun"]
Explanation: The restaurant they both like and have the least index sum is "Shogun" with index sum 1 (0+1).
```

**Note:**  

1.  The length of both lists will be in the range of [1, 1000].
2.  The length of strings in both lists will be in the range of [1, 30].
3.  The index is starting from 0 to the list length minus 1.
4.  No duplicates in both lists.


#### Solution

Language: **Python**

```python
class Solution(object):
    def findRestaurant(self, list1, list2):
        """
        :type list1: List[str]
        :type list2: List[str]
        :rtype: List[str]
        """
        ans = []
        idx = float('inf')
        d = {}
        if len(list2) < len(list1):
            list1, list2 = list2, list1
        for i in range(len(list2)):
            d[list2[i]] = i
        for i, w in enumerate(list1):
            if w in d:
                cur = i + d[w]
                if cur < idx:
                    ans = [w]
                    idx = cur
                elif cur == idx:
                    ans.append(w)
        return ans
```
#### Notes
- do not use `if w in list2:` directly, the time complexity would be O(n*m)
- transfer list2 to dict, time complexity would be reduced to O(n)
