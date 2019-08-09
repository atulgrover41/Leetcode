---
id: search-in-a-binary-search-tree
title: Search in a Binary Search Tree
sidebar_label: Search in a Binary Search Tree
---
## Description
<div class="description">
<p>Given the root node of a binary search tree (BST) and a value. You need to find the node in the BST that the node&#39;s value equals the given value. Return the subtree rooted with that node. If such node doesn&#39;t exist, you should return NULL.</p>

<p>For example,&nbsp;</p>

<pre>
Given the tree:
        4
       / \
      2   7
     / \
    1   3

And the value to search: 2
</pre>

<p>You should return this subtree:</p>

<pre>
      2     
     / \   
    1   3
</pre>

<p>In the example above, if we want to search the value <code>5</code>, since there is no node with value <code>5</code>, we should return <code>NULL</code>.</p>

<p>Note that an empty tree is represented by <code>NULL</code>, therefore you would see the expected output (serialized tree format) as&nbsp;<code>[]</code>, not <code>null</code>.</p>

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
    def searchBST(self, root: TreeNode, val: int) -> TreeNode:
        if root is None:
            return None
        if val ==root.val:
            return root
        elif val < root.val:
            return self.searchBST(root.left,val)
        else:
            return self.searchBST(root.right,val)
            

```