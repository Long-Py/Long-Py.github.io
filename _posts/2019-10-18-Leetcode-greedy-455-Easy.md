---
layout: post
title: '455. Assign Cookies'
subtitle: ''
date: 2019-10-18
categories: Leetcode
tags: Leetcode Greedy Array
---
### [455\. Assign Cookies](https://leetcode.com/problems/assign-cookies/)

Difficulty: **Easy**

Topics: **Greedy**

Assume you are an awesome parent and want to give your children some cookies. But, you should give each child at most one cookie. Each child i has a greed factor g<sub style="display: inline;">i</sub>, which is the minimum size of a cookie that the child will be content with; and each cookie j has a size s<sub style="display: inline;">j</sub>. If s<sub style="display: inline;">j</sub> >= g<sub style="display: inline;">i</sub>, we can assign the cookie j to the child i, and the child i will be content. Your goal is to maximize the number of your content children and output the maximum number.

**Note:**  
You may assume the greed factor is always positive.  
You cannot assign more than one cookie to one child.

**Example 1:**  

```
Input: [1,2,3], [1,1]

Output: 1

Explanation: You have 3 children and 2 cookies. The greed factors of 3 children are 1, 2, 3\. 
And even though you have 2 cookies, since their size is both 1, you could only make the child whose greed factor is 1 content.
You need to output 1.
```

**Example 2:**  

```
Input: [1,2], [1,2,3]

Output: 2

Explanation: You have 2 children and 3 cookies. The greed factors of 2 children are 1, 2\. 
You have 3 cookies and their sizes are big enough to gratify all of the children, 
You need to output 2.
```


#### Solution

Language: **Python**

```python
class Solution(object):
    def findContentChildren(self, g, s):
        """
        :type g: List[int]
        :type s: List[int]
        :rtype: int
        """
        if not s or not g: return 0
        lg = len(g)
        lx = len(s)
        g = sorted(g)
        s = sorted(s)
        ig, ix = lg-1, lx-1
        ans = 0
        while ig >= 0 and ix >= 0:
            if g[ig] <= s[ix]:
                ans += 1
                ix -= 1
            ig -= 1
        return ans
```