---
id: kth-smallest-element-in-a-bst
title: Kth Smallest Element in a BST
sidebar_label: Kth Smallest Element in a BST
---
## Description
<div class="description">
<p>Given a binary search tree, write a function <code>kthSmallest</code> to find the <b>k</b>th smallest element in it.</p>

<p><b>Note: </b><br />
You may assume k is always valid, 1 &le; k &le; BST&#39;s total elements.</p>

<p><strong>Example 1:</strong></p>

<pre>
<strong>Input:</strong> root = [3,1,4,null,2], k = 1
   3
  / \
 1   4
  \
&nbsp;  2
<strong>Output:</strong> 1</pre>

<p><strong>Example 2:</strong></p>

<pre>
<strong>Input:</strong> root = [5,3,6,2,4,null,null,1], k = 3
       5
      / \
     3   6
    / \
   2   4
  /
 1
<strong>Output:</strong> 3
</pre>

<p><b>Follow up:</b><br />
What if the BST is modified (insert/delete operations) often and you need to find the kth smallest frequently? How would you optimize the kthSmallest routine?</p>

</div>

## Solution(python3)
```python3
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, x):
#         self.val = x
#         self.left = None
#         self.right = None

class Solution:
    def kthSmallest(self, root: TreeNode, k: int) -> int:
        value=[]
        def inorder(root,value):
            if root: 
                if root.left:
                    value=inorder(root.left,value)
                
                value.append(root.val)
            
            
                if root.right:
                    value=inorder(root.right,value)
            return value
        value=inorder(root,value)
        return value[k-1]
        
```