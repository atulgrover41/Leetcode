---
id: average-of-levels-in-binary-tree
title: Average of Levels in Binary Tree
sidebar_label: Average of Levels in Binary Tree
---
## Description
<div class="description">
Given a non-empty binary tree, return the average value of the nodes on each level in the form of an array.

<p><b>Example 1:</b><br />
<pre>
<b>Input:</b>
    3
   / \
  9  20
    /  \
   15   7
<b>Output:</b> [3, 14.5, 11]
<b>Explanation:</b>
The average value of nodes on level 0 is 3,  on level 1 is 14.5, and on level 2 is 11. Hence return [3, 14.5, 11].
</pre>
</p>

<p><b>Note:</b><br>
<ol>
<li>The range of node's value is in the range of 32-bit signed integer.</li>
</ol>
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
    def averageOfLevels(self, root: TreeNode) -> List[float]:
        current=[root]
        value=[]
        temp=0
        next_level=[]
        prev_length=1
        while current:
            current_node=current.pop()
            
            if current_node.left:
                next_level.append(current_node.left)
            if current_node.right:
                next_level.append(current_node.right)
            temp+=current_node.val
            if len(current) == 0 and len(next_level) !=None:
                temp/=prev_length
                current=copy.copy(next_level)
                prev_length = len(next_level)
                del next_level[:]
                value.append(temp)
                temp=0
        return value
                
```