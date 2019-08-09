---
id: range-sum-query-immutable
title: Range Sum Query - Immutable
sidebar_label: Range Sum Query - Immutable
---
## Description
<div class="description">
<p>Given an integer array <i>nums</i>, find the sum of the elements between indices <i>i</i> and <i>j</i> (<i>i</i> &le; <i>j</i>), inclusive.</p>

<p><b>Example:</b><br>
<pre>
Given nums = [-2, 0, 3, -5, 2, -1]

sumRange(0, 2) -> 1
sumRange(2, 5) -> -1
sumRange(0, 5) -> -3
</pre>
</p>

<p><b>Note:</b><br>
<ol>
<li>You may assume that the array does not change.</li>
<li>There are many calls to <i>sumRange</i> function.</li>
</ol>
</p>
</div>

## Solution(python3)
```python3
class NumArray:

    def __init__(self, nums: List[int]):
        self.num=nums

    def sumRange(self, i: int, j: int) -> int:
        su=0
        numss= self.num[i:j+1]
        return sum(numss)

# Your NumArray object will be instantiated and called as such:
# obj = NumArray(nums)
# param_1 = obj.sumRange(i,j)
```