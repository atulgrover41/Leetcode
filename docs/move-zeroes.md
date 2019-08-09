---
id: move-zeroes
title: Move Zeroes
sidebar_label: Move Zeroes
---
## Description
<div class="description">
<p>Given an array <code>nums</code>, write a function to move all <code>0</code>&#39;s to the end of it while maintaining the relative order of the non-zero elements.</p>

<p><b>Example:</b></p>

<pre>
<b>Input:</b> <code>[0,1,0,3,12]</code>
<b>Output:</b> <code>[1,3,12,0,0]</code></pre>

<p><b>Note</b>:</p>

<ol>
	<li>You must do this <b>in-place</b> without making a copy of the array.</li>
	<li>Minimize the total number of operations.</li>
</ol>
</div>

## Solution(python3)
```python3
class Solution:
    def moveZeroes(self, nums: List[int]) -> None:
        """
        Do not return anything, modify nums in-place instead.
        """
        x=len(nums)
        for y in range(0,x):
            i=nums[y]
            if i == 0:
                nums.remove(i)
                nums.append(i)
            
```