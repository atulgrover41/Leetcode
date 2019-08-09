---
id: minimum-absolute-difference-in-bst
title: Minimum Absolute Difference in BST
sidebar_label: Minimum Absolute Difference in BST
---
## Description
<div class="description">
<p>Given a binary search tree with non-negative values, find the minimum <a href="https://en.wikipedia.org/wiki/Absolute_difference">absolute difference</a> between values of any two nodes.</p>

<p><b>Example:</b></p>

<pre>
<b>Input:</b>

   1
    \
     3
    /
   2

<b>Output:</b>
1

<b>Explanation:</b>
The minimum absolute difference is 1, which is the difference between 2 and 1 (or between 2 and 3).
</pre>

<p>&nbsp;</p>

<p><b>Note:</b> There are at least two nodes in this BST.</p>
</div>

## Solution(python3)
```python3
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, x):
#         self.val = x
#         self.left = None
#         self.right = None
def bfs(root):
    to_visit=[root]
    senback=[root.val]
    while to_visit:
        current=to_visit.pop()
        if current.left:
            to_visit.append(current.left)
            senback.append(current.left.val)
        if current.right:
            to_visit.append(current.right)
            senback.append(current.right.val)
    return senback
            
class Solution:
    def getMinimumDifference(self, root: TreeNode) -> int:
        returned=bfs(root)
        minlist=[]
        for i in range(0,len(returned)):
            for j in range(i+1,len(returned)):
                minlist.append(abs(returned[i]-returned[j]))
                if abs(returned[i]-returned[j]) ==1:
                    return 1
        minlist=sorted(minlist)
        return minlist[0]
```