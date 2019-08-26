---
layout: post
title: '1169. Invalid Transactions'
subtitle: ''
date: 2019-08-25
categories: Leetcode
tags: Leetcode Array
---
### [1169\. Invalid Transactions](https://leetcode.com/problems/invalid-transactions/)

Difficulty: **Easy**

Topics: **Array**

A transaction is _possibly invalid_ if:

*   the amount exceeds $1000, or;
*   if it occurs within (and including) 60 minutes of another transaction with the same name in a different city.

Each transaction string `transactions[i]` consists of comma separated values representing the name, time (in minutes), amount, and city of the transaction.

Given a list of `transactions`, return a list of transactions that are possibly invalid.  You may return the answer in any order.

**Example 1:**

```
Input: transactions = ["alice,20,800,mtv","alice,50,100,beijing"]
Output: ["alice,20,800,mtv","alice,50,100,beijing"]
Explanation: The first transaction is invalid because the second transaction occurs within a difference of 60 minutes, have the same name and is in a different city. Similarly the second one is invalid too.
```

**Example 2:**

```
Input: transactions = ["alice,20,800,mtv","alice,50,1200,mtv"]
Output: ["alice,50,1200,mtv"]
```

**Example 3:**

```
Input: transactions = ["alice,20,800,mtv","bob,50,1200,mtv"]
Output: ["bob,50,1200,mtv"]
```

**Constraints:**

*   `transactions.length <= 1000`
*   Each `transactions[i]` takes the form `"{name},{time},{amount},{city}"`
*   Each `{name}` and `{city}` consist of lowercase English letters, and have lengths between `1` and `10`.
*   Each `{time}` consist of digits, and represent an integer between `0` and `1000`.
*   Each `{amount}` consist of digits, and represent an integer between `0` and `2000`.


#### Solution

Language: **Python**

```python
class Solution(object):
    def invalidTransactions(self, transactions):
        """
        :type transactions: List[str]
        :rtype: List[str]
        """
        T = []
        for t in transactions:
            temp = t.split(',')
            temp[1] = int(temp[1])
            temp[2] = int(temp[2])
            T.append(temp)
​
        invalidT = []
        for t in T:
            if t[2] > 1000:
                t[1] = str(t[1])
                t[2] = str(t[2])
                invalidT.append(','.join(t))
                continue
            for x in T:
                if t[0] == x[0] and abs(t[1] - int(x[1])) <= 60 and t[3] != x[3]:                
                    t[1] = str(t[1])
                    t[2] = str(t[2])
                    invalidT.append(','.join(t))
                    break
​
        return invalidT        
```