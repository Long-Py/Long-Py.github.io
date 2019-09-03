---
layout: post
title: '203. Remove Linked List Elements'
subtitle: ''
date: 2019-09-02
categories: Leetcode
tags: Leetcode LinkedList
---
### [203\. Remove Linked List Elements](https://leetcode.com/problems/remove-linked-list-elements/)

Difficulty: **Easy**

Topics: **Linked List**


Remove all elements from a linked list of integers that have value **_val_**.

**Example:**

```
Input:  1->2->6->3->4->5->6, val = 6
Output: 1->2->3->4->5
```


#### Solution

Language: **Python**

```python
# Definition for singly-linked list.
# class ListNode(object):
#     def __init__(self, x):
#         self.val = x
#         self.next = None
​
class Solution(object):
    def removeElements(self, head, val):
        """
        :type head: ListNode
        :type val: int
        :rtype: ListNode
        """
        dummy = ListNode(-1)
        dummy.next = head
        cur = dummy
        while cur.next:
            if cur.next.val == val:
                cur.next = cur.next.next
            else:
                cur = cur.next
        return dummy.next
            
        """
```
#### Notes
- keep prev and track next.