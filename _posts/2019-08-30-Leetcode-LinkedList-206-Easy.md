---
layout: post
title: '206. Reverse Linked List'
subtitle: ''
date: 2019-08-30
categories: Leetcode
tags: Leetcode LinkedList
---
### [206\. Reverse Linked List](https://leetcode.com/problems/reverse-linked-list/)

Difficulty: **Easy**

Topics: **LinkedList**


Reverse a singly linked list.

**Example:**

```
Input: 1->2->3->4->5->NULL
Output: 5->4->3->2->1->NULL
```

**Follow up:**

A linked list can be reversed either iteratively or recursively. Could you implement both?


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
    def reverseList(self, head):
        """
        :type head: ListNode
        :rtype: ListNode
        """
        pre = None
        cur = head
        while cur:
            next = cur.next
            cur.next = pre
            pre = cur
            cur = next
        return pre
```
#### Notes
- use `next` to hold cur.next
- reverse: 
  - cur.next -> prev
  - prev -> cur
  - cur -> next

