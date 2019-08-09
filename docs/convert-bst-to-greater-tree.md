---
id: convert-bst-to-greater-tree
title: Convert BST to Greater Tree
sidebar_label: Convert BST to Greater Tree
---
## Description
<div class="description">
<p>Given a Binary Search Tree (BST), convert it to a Greater Tree such that every key of the original BST is changed to the original key plus sum of all keys greater than the original key in BST.</p>

<p>
<b>Example:</b>
<pre>
<b>Input:</b> The root of a Binary Search Tree like this:
              5
            /   \
           2     13

<b>Output:</b> The root of a Greater Tree like this:
             18
            /   \
          20     13
</pre>
</p>
</div>

## Solution(python)
```python
# Definition for a binary tree node.
# class TreeNode(object):
#     def __init__(self, x):
#         self.val = x
#         self.left = None
#         self.right = None

class Solution(object):
    def dfs(self,root,val):
        if root.left:
            val=self.dfs(root.left,val)
        val.append(root.val)
        if root.right:
            val=self.dfs(root.right,val)
        return val
    
    def secdfs(self,root,x):
        if root.left:
            x=self.secdfs(root.left,x)
        x=x-root.val
        root.val=x+root.val
        if root.right:
            x=self.secdfs(root.right,x)
        return x
    
    
    def convertBST(self, root):
        """
        :type root: TreeNode
        :rtype: TreeNode
        """
        if root is None:
            return root
        val=[]
        val=self.dfs(root,val)
        x=sum(val)
        self.secdfs(root,x)
        return root
    
```