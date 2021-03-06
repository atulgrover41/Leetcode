---
id: palindrome-linked-list
title: Palindrome Linked List
sidebar_label: Palindrome Linked List
---
## Description
<div class="description">
<p>Given a singly linked list, determine if it is a palindrome.</p>

<p><strong>Example 1:</strong></p>

<pre>
<strong>Input:</strong> 1-&gt;2
<strong>Output:</strong> false</pre>

<p><strong>Example 2:</strong></p>

<pre>
<strong>Input:</strong> 1-&gt;2-&gt;2-&gt;1
<strong>Output:</strong> true</pre>

<p><b>Follow up:</b><br />
Could you do it in O(n) time and O(1) space?</p>

</div>

## Solution(python)
```python
# Definition for singly-linked list.
# class ListNode(object):
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution(object):
    def isPalindrome(self, head):
        """
        :type head: ListNode
        :rtype: bool
        """
        if head is None:
            return True
        l=[]
        while head != None:
            l.append(head.val)
            head=head.next        
        newl=copy.copy(l)
        newl.reverse()
        for i,j in zip(l,newl):
            if i != j:
                return False
        return True
```