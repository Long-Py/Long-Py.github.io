---
layout: post
title: '860. Lemonade Change'
subtitle: ''
date: 2019-10-18
categories: Leetcode
tags: Leetcode Greedy Array
---
### [860\. Lemonade Change](https://leetcode.com/problems/lemonade-change/)

Difficulty: **Easy**

Topics: **Greedy**


At a lemonade stand, each lemonade costs `$5`. 

Customers are standing in a queue to buy from you, and order one at a time (in the order specified by `bills`).

Each customer will only buy one lemonade and pay with either a `$5`, `$10`, or `$20` bill.  You must provide the correct change to each customer, so that the net transaction is that the customer pays $5.

Note that you don't have any change in hand at first.

Return `true` if and only if you can provide every customer with correct change.


**Example 1:**

```
Input: [5,5,5,10,20]
Output: true
Explanation: 
From the first 3 customers, we collect three $5 bills in order.
From the fourth customer, we collect a $10 bill and give back a $5.
From the fifth customer, we give a $10 bill and a $5 bill.
Since all customers got correct change, we output true.
```


**Example 2:**

```
Input: [5,5,10]
Output: true
```


**Example 3:**

```
Input: [10,10]
Output: false
```


**Example 4:**

```
Input: [5,5,10,10,20]
Output: false
Explanation: 
From the first two customers in order, we collect two $5 bills.
For the next two customers in order, we collect a $10 bill and give back a $5 bill.
For the last customer, we can't give change of $15 back because we only have two $10 bills.
Since not every customer received correct change, the answer is false.
```

**<span style="display: inline;">Note:</span>**

*   `0 <= bills.length <= 10000`
*   `bills[i]` will be either `5`, `10`, or `20`.


#### Solution

Language: **Python**

```python
class Solution(object):
    def lemonadeChange(self, bills):
        """
        :type bills: List[int]
        :rtype: bool
        """
        d = {5:0,10:0,20:0}
        
        for i in bills:
            if i == 5:
                d[5] = d.get(5, 0) + 1
            elif i == 10:
                if d[5] < 1:
                    return False
                else:
                    d[5] -= 1
                    d[10] = d.get(10, 0) + 1
            else:
                if d[10] == 0:
                    if d[5] < 3:
                        return False
                    else:
                        d[5] -=3
                        d[20] = d.get(20, 0) + 1
                else:
                    if d[5] < 1:
                        return False
                    else:
                        d[5] -= 1
                        d[10] -= 1
                        d[20] = d.get(20, 0) + 1
        return True
```