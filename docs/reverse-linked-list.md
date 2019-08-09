---
id: reverse-linked-list
title: Reverse Linked List
sidebar_label: Reverse Linked List
---
## Description
<div class="description">
<p>Reverse a singly linked list.</p>

<p><strong>Example:</strong></p>

<pre>
<strong>Input:</strong> 1-&gt;2-&gt;3-&gt;4-&gt;5-&gt;NULL
<strong>Output:</strong> 5-&gt;4-&gt;3-&gt;2-&gt;1-&gt;NULL
</pre>

<p><b>Follow up:</b></p>

<p>A linked list can be reversed either iteratively or recursively. Could you implement both?</p>

</div>

## Solution(python3)
```python3
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution:
    def reverseList(self, head: ListNode) -> ListNode:
        prev_node =None
        while head:
            next_node =head.next 
            head.next =prev_node 
            prev_node =head
            head = next_node 
            
        return prev_node 
```