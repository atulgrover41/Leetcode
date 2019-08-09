---
id: sort-list
title: Sort List
sidebar_label: Sort List
---
## Description
<div class="description">
<p>Sort a linked list in <em>O</em>(<em>n</em> log <em>n</em>) time using constant space complexity.</p>

<p><strong>Example 1:</strong></p>

<pre>
<strong>Input:</strong> 4-&gt;2-&gt;1-&gt;3
<strong>Output:</strong> 1-&gt;2-&gt;3-&gt;4
</pre>

<p><strong>Example 2:</strong></p>

<pre>
<strong>Input:</strong> -1-&gt;5-&gt;3-&gt;4-&gt;0
<strong>Output:</strong> -1-&gt;0-&gt;3-&gt;4-&gt;5</pre>

</div>

## Solution(python3)
```python3
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution:
    def sortList(self, head: ListNode) -> ListNode:
        new_node=head
        l=[]
        while new_node:
            l.append(new_node.val)
            new_node=new_node.next
        l=sorted(l)
        new_node=head
        while new_node:
            new_node.val=l.pop(0)
            new_node=new_node.next
        return head
```