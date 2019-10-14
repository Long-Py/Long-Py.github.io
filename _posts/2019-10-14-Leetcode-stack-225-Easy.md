---
layout: post
title: '225. Implement Stack using Queues'
subtitle: ''
date: 2019-10-14
categories: Leetcode
tags: Leetcode Stack
---
### [225\. Implement Stack using Queues](https://leetcode.com/problems/implement-stack-using-queues/)

Difficulty: **Easy**

Topics: **Stack**

Implement the following operations of a stack using queues.

*   push(x) -- Push element x onto stack.
*   pop() -- Removes the element on top of the stack.
*   top() -- Get the top element.
*   empty() -- Return whether the stack is empty.

**Example:**

```
MyStack stack = new MyStack();

stack.push(1);
stack.push(2);  
stack.top();   // returns 2
stack.pop();   // returns 2
stack.empty(); // returns false
```

**Notes:**

*   You must use _only_ standard operations of a queue -- which means only `push to back`, `peek/pop from front`, `size`, and `is empty` operations are valid.
*   Depending on your language, queue may not be supported natively. You may simulate a queue by using a list or deque (double-ended queue), as long as you use only standard operations of a queue.
*   You may assume that all operations are valid (for example, no pop or top operations will be called on an empty stack).


#### Solution

Language: **Python**

```python
class MyStack(object):
​
    def __init__(self):
        self._queue = collections.deque()
​
    def push(self, x):
        q = self._queue
        q.append(x)
        for _ in range(len(q) - 1):
            q.append(q.popleft())
        
    def pop(self):
        return self._queue.popleft()
​
    def top(self):
        return self._queue[0]
    
    def empty(self):
        return not len(self._queue)
        
​
​
# Your MyStack object will be instantiated and called as such:
# obj = MyStack()
# obj.push(x)
# param_2 = obj.pop()
# param_3 = obj.top()
# param_4 = obj.empty()
```