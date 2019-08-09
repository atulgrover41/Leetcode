---
id: add-two-numbers
title: Add Two Numbers
sidebar_label: Add Two Numbers
---
## Description
<div class="description">
<p>You are given two <b>non-empty</b> linked lists representing two non-negative integers. The digits are stored in <b>reverse order</b> and each of their nodes contain a single digit. Add the two numbers and return it as a linked list.</p>

<p>You may assume the two numbers do not contain any leading zero, except the number 0 itself.</p>

<p><b>Example:</b></p>

<pre>
<b>Input:</b> (2 -&gt; 4 -&gt; 3) + (5 -&gt; 6 -&gt; 4)
<b>Output:</b> 7 -&gt; 0 -&gt; 8
<b>Explanation:</b> 342 + 465 = 807.
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
    def addTwoNumbers(self, l1: ListNode, l2: ListNode) -> ListNode:
        number1=""
        number2=""
        while l1!=None:
            number1+=str(l1.val)
            l1=l1.next
        while l2!=None:
            number2+=str(l2.val)
            l2=l2.next
        number1=number1[::-1]
        number2=number2[::-1]
        number3=int(number2)+int(number1)
        number3=str(number3)[::-1]
        head=None
        Tail=None
        for i in number3:
            x=ListNode(int(i))
            if head == None: 
                head=x
                Tail=x
            else:
                Tail.next=x
                Tail=x
        return head
```