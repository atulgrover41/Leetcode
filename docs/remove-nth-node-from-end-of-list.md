---
id: remove-nth-node-from-end-of-list
title: Remove Nth Node From End of List
sidebar_label: Remove Nth Node From End of List
---
## Description
<div class="description">
<p>Given a linked list, remove the <em>n</em>-th node from the end of list and return its head.</p>

<p><strong>Example:</strong></p>

<pre>
Given linked list: <strong>1-&gt;2-&gt;3-&gt;4-&gt;5</strong>, and <strong><em>n</em> = 2</strong>.

After removing the second node from the end, the linked list becomes <strong>1-&gt;2-&gt;3-&gt;5</strong>.
</pre>

<p><strong>Note:</strong></p>

<p>Given <em>n</em> will always be valid.</p>

<p><strong>Follow up:</strong></p>

<p>Could you do this in one pass?</p>

</div>

## Solution(python3)
```python3
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, x):
#         self.val = x
#         self.next = None
class Solution:
    def removeNthFromEnd(self, head: ListNode, n: int) -> ListNode:
        length=1
        node=head
        while node.next!=None:
            length+=1
            node =node.next
        node=head
        if length ==1:
            return None
        if length == n:
            return head.next
        while length -n !=1:
            node=node.next
            length -=1
        node.next= node.next.next
        return head
        
```