---
id: same-tree
title: Same Tree
sidebar_label: Same Tree
---
## Description
<div class="description">
<p>Given two binary trees, write a function to check if they are the same or not.</p>

<p>Two binary trees are considered the same if they are structurally identical and the nodes have the same value.</p>

<p><strong>Example 1:</strong></p>

<pre>
<strong>Input:</strong>     1         1
          / \       / \
         2   3     2   3

        [1,2,3],   [1,2,3]

<strong>Output:</strong> true
</pre>

<p><strong>Example 2:</strong></p>

<pre>
<strong>Input:</strong>     1         1
          /           \
         2             2

        [1,2],     [1,null,2]

<strong>Output:</strong> false
</pre>

<p><strong>Example 3:</strong></p>

<pre>
<strong>Input:</strong>     1         1
          / \       / \
         2   1     1   2

        [1,2,1],   [1,1,2]

<strong>Output:</strong> false
</pre>

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
    def isSameTree(self, p: TreeNode, q: TreeNode) -> bool:
        def bfs(root):
            if not root:
                return []

            node=[root]
            value=[root.val]
            while node:
                currentnode =node.pop(0)
                
                print(currentnode.val)
                if currentnode.left:
                    node.append(currentnode.left)
                    value.append(currentnode.left.val)
                else:
                    value.append(None)
                if currentnode.right:
                    node.append(currentnode.right)
                    value.append(currentnode.right.val)
                else:
                    value.append(None)
            return value
        v1= bfs(p)
        v2= bfs(q)
        #print(v1,v2)
        return True if v1==v2 else False
```