---
id: two-sum-iv-input-is-a-bst
title: Two Sum IV - Input is a BST
sidebar_label: Two Sum IV - Input is a BST
---
## Description
<div class="description">
<p>Given a Binary Search Tree and a target number, return true if there exist two elements in the BST such that their sum is equal to the given target.</p>

<p><b>Example 1:</b></p>

<pre>
<b>Input:</b> 
    5
   / \
  3   6
 / \   \
2   4   7

Target = 9

<b>Output:</b> True
</pre>

<p>&nbsp;</p>

<p><b>Example 2:</b></p>

<pre>
<b>Input:</b> 
    5
   / \
  3   6
 / \   \
2   4   7

Target = 28

<b>Output:</b> False
</pre>

<p>&nbsp;</p>

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
    def findTarget(self, root, k):
        """
        :type root: TreeNode
        :type k: int
        :rtype: bool
        """
        lis=set()
        def dfs(root,lis):
            if root.left:
                lis=dfs(root.left,lis)
            lis.add(root.val)
            if root.right:
                lis=dfs(root.right,lis)
            return lis
        
        lis=dfs(root,lis)
        for i in lis:
            if k-i in lis and k-i != i:
                return True
            
        return False
```