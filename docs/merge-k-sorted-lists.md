---
id: merge-k-sorted-lists
title: Merge k Sorted Lists
sidebar_label: Merge k Sorted Lists
---
## Description
<div class="description">
<p>Merge <em>k</em> sorted linked lists and return it as one sorted list. Analyze and describe its complexity.</p>

<p><strong>Example:</strong></p>

<pre>
<strong>Input:</strong>
[
&nbsp; 1-&gt;4-&gt;5,
&nbsp; 1-&gt;3-&gt;4,
&nbsp; 2-&gt;6
]
<strong>Output:</strong> 1-&gt;1-&gt;2-&gt;3-&gt;4-&gt;4-&gt;5-&gt;6
</pre>

</div>

## Solution(python3)
```python3
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, x):
#         self.val = x
#         self.next = None


class Solution:
    def mergeKLists(self, lists: List[ListNode]) -> ListNode:
        if len(lists) is 0:
            return None
        #print(len(lists))
        h=[]
        for i in lists:
            while i!=None:
                heapq.heappush(h, i.val)
                i=i.next
        head= None
        while len(h)>0:
            if head ==None:
                i=heapq.heappop(h)
                newnode=ListNode(i)
                head=newnode
                root=newnode
            else:
                i=heapq.heappop(h)
                newnode=ListNode(i)
                root.next=newnode
                root=newnode
        return head
```