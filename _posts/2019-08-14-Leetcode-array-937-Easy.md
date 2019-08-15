---
layout: post
title: '937. Reorder Log Files'
subtitle: ''
date: 2019-08-14
categories: Leetcode
tags: Leetcode Array
---
### [937\. Reorder Log Files](https://leetcode.com/problems/reorder-log-files/)

Difficulty: **Easy**

Topics: **Array**


You have an array of `logs`.  Each log is a space delimited string of words.

For each log, the first word in each log is an alphanumeric _identifier_.  Then, either:

*   Each word after the identifier will consist only of lowercase letters, or;
*   Each word after the identifier will consist only of digits.

We will call these two varieties of logs _letter-logs_ and _digit-logs_.  It is guaranteed that each log has at least one word after its identifier.

Reorder the logs so that all of the letter-logs come before any digit-log.  The letter-logs are ordered lexicographically ignoring identifier, with the identifier used in case of ties.  The digit-logs should be put in their original order.

Return the final order of the logs.


**Example 1:**

```
Input: ["a1 9 2 3 1","g1 act car","zo4 4 7","ab1 off key dog","a8 act zoo"]
Output: ["g1 act car","a8 act zoo","ab1 off key dog","a1 9 2 3 1","zo4 4 7"]
```

**Note:**

1.  `0 <= logs.length <= 100`
2.  `3 <= logs[i].length <= 100`
3.  `logs[i]` is guaranteed to have an identifier, and a word after the identifier.


#### Solution

Language: **Python**

```python
class Solution(object):
    def reorderLogFiles(self, logs):
        """
        :type logs: List[str]
        :rtype: List[str]
        """
        def mySort(log):
            id, rest = log.split(' ', 1)
            if rest[0].isdigit():
                return (1,)
            else:
                return(0,rest,id)
        return sorted(logs,key=mySort)
```

#### Notes
- The `split(separator, max)` method splits a string into a list. You can specify the separator, **default** separator is any whitespace.
- `max`: Optional. Specifies how many splits to do. Default value is -1, which is "all occurrences". Setting the max parameter to 1, will return a list with 2 elements!
- If the log is a digit log, label it as 1; label an alpha log as 0, sort it by content and then id.