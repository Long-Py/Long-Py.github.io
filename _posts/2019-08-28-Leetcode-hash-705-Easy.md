---
layout: post
title: '705. Design HashSet'
subtitle: ''
date: 2019-08-28
categories: Leetcode
tags: Leetcode Array HashTable
---
### [705\. Design HashSet](https://leetcode.com/problems/design-hashset/)

Difficulty: **Easy**

Topics: **HashTable**


Design a HashSet without using any built-in hash table libraries.

To be specific, your design should include these functions:

*   `add(value)`: Insert a value into the HashSet. 
*   `contains(value)` : Return whether the value exists in the HashSet or not.
*   `remove(value)`: Remove a value in the HashSet. If the value does not exist in the HashSet, do nothing.

**Example:**

```
MyHashSet hashSet = new MyHashSet();
hashSet.add(1);         
hashSet.add(2);         
hashSet.contains(1);    // returns true
hashSet.contains(3);    // returns false (not found)
hashSet.add(2);          
hashSet.contains(2);    // returns true
hashSet.remove(2);          
hashSet.contains(2);    // returns false (already removed)
```

**Note:**

*   All values will be in the range of `[0, 1000000]`.
*   The number of operations will be in the range of `[1, 10000]`.
*   Please do not use the built-in HashSet library.


#### Solution

Language: **Python**

```python
class MyHashSet(object):
​
    def __init__(self):
        """
        Initialize your data structure here.
        """
        self.l = [None]*1000000
​
    def add(self, key):
        """
        :type key: int
        :rtype: None
        """
        if self.l[key] is None:
            self.l[key] = key
​
    def remove(self, key):
        """
        :type key: int
        :rtype: None
        """
        if self.l[key] is None:
            return
        else:
            self.l[key] = None
​
    def contains(self, key):
        """
        Returns true if this set contains the specified element
        :type key: int
        :rtype: bool
        """
        return not self.l[key] == None
        
​
​
# Your MyHashSet object will be instantiated and called as such:
# obj = MyHashSet()
# obj.add(key)
# obj.remove(key)
# param_3 = obj.contains(key)
```