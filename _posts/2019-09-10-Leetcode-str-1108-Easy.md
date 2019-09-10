---
layout: post
title: '1108. Defanging an IP Address'
subtitle: ''
date: 2019-09-10
categories: Leetcode
tags: Leetcode Strings
---
### [1108\. Defanging an IP Address](https://leetcode.com/problems/defanging-an-ip-address/)

Difficulty: **Easy**

Topics: **Strings**


Given a valid (IPv4) IP `address`, return a defanged version of that IP address.

A _defanged IP address_ replaces every period `"."` with `"[.]"`.

**Example 1:**

```
Input: address = "1.1.1.1"
Output: "1[.]1[.]1[.]1"
```

**Example 2:**

```
Input: address = "255.100.50.0"
Output: "255[.]100[.]50[.]0"
```

**Constraints:**

*   The given `address` is a valid IPv4 address.


#### Solution

Language: **Python**

```python
class Solution(object):
    def defangIPaddr(self, address):
        """
        :type address: str
        :rtype: str
        """
        return address.replace('.','[.]')
    
    
```