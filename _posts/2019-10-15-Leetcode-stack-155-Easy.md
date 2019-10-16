---
layout: post
title: '155. Min Stack'
subtitle: ''
date: 2019-10-15
categories: Leetcode
tags: Leetcode Stack
---
### [155\. Min Stack](https://leetcode.com/problems/min-stack/)

Difficulty: **Easy**

Topics: **Stack**

Design a stack that supports push, pop, top, and retrieving the minimum element in constant time.

*   push(x) -- Push element x onto stack.
*   pop() -- Removes the element on top of the stack.
*   top() -- Get the top element.
*   getMin() -- Retrieve the minimum element in the stack.

**Example:**

```
MinStack minStack = new MinStack();
minStack.push(-2);
minStack.push(0);
minStack.push(-3);
minStack.getMin();   --> Returns -3.
minStack.pop();
minStack.top();      --> Returns 0.
minStack.getMin();   --> Returns -2.
```


#### Solution

Language: **Python**

```python
class MinStack(object):
​
    def __init__(self):
        self.stack = [(-1, float('inf'))]
​
    def push(self, x):
        self.stack.append([x, min(x, self.stack[-1][1])])
​
    def pop(self):
        if len(self.stack) > 1: self.stack.pop()
​
    def top(self):
        if len(self.stack) == 1: return None
        return self.stack[-1][0]
​
    def getMin(self):
        return self.stack[-1][1]
​
​
# Your MinStack object will be instantiated and called as such:
# obj = MinStack()
# obj.push(x)
# obj.pop()
# param_3 = obj.top()
# param_4 = obj.getMin()
```