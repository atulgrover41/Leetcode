---
id: construct-string-from-binary-tree
title: Construct String from Binary Tree
sidebar_label: Construct String from Binary Tree
---
## Description
<div class="description">
<p>You need to construct a string consists of parenthesis and integers from a binary tree with the preorder traversing way.</p>

<p>The null node needs to be represented by empty parenthesis pair "()". And you need to omit all the empty parenthesis pairs that don't affect the one-to-one mapping relationship between the string and the original binary tree.</p>

<p><b>Example 1:</b><br />
<pre>
<b>Input:</b> Binary tree: [1,2,3,4]
       1
     /   \
    2     3
   /    
  4     

<b>Output:</b> "1(2(4))(3)"
<br/><b>Explanation:</b> Originallay it needs to be "1(2(4)())(3()())", <br/>but you need to omit all the unnecessary empty parenthesis pairs. <br/>And it will be "1(2(4))(3)".
</pre>
</p>

<p><b>Example 2:</b><br />
<pre>
<b>Input:</b> Binary tree: [1,2,3,null,4]
       1
     /   \
    2     3
     \  
      4 

<b>Output:</b> "1(2()(4))(3)"
<br/><b>Explanation:</b> Almost the same as the first example, <br/>except we can't omit the first parenthesis pair to break the one-to-one mapping relationship between the input and the output.
</pre>
</p>
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
    def tree2str(self, t: TreeNode) -> str:
        s=""
        if not t:
            return s
        def dfs(root,s):
            s+=str(root.val)
            
            if root.left:
                s+="("
                s=dfs(root.left,s)
                s+=")"
            if not root.left and root.right:
                s+="()"
            if root.right:
                s+="("
                s=dfs(root.right,s)
                s+=")"
            return s
        s=dfs(t,s)
        return s
```