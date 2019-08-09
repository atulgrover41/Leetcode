---
id: find-minimum-in-rotated-sorted-array
title: Find Minimum in Rotated Sorted Array
sidebar_label: Find Minimum in Rotated Sorted Array
---
## Description
<div class="description">
<p>Suppose an array sorted in ascending order is rotated at some pivot unknown to you beforehand.</p>

<p>(i.e., &nbsp;<code>[0,1,2,4,5,6,7]</code>&nbsp;might become &nbsp;<code>[4,5,6,7,0,1,2]</code>).</p>

<p>Find the minimum element.</p>

<p>You may assume no duplicate exists in the array.</p>

<p><strong>Example 1:</strong></p>

<pre>
<strong>Input:</strong> [3,4,5,1,2] 
<strong>Output:</strong> 1
</pre>

<p><strong>Example 2:</strong></p>

<pre>
<strong>Input:</strong> [4,5,6,7,0,1,2]
<strong>Output:</strong> 0
</pre>

</div>

## Solution(python3)
```python3
class Solution:
    def findMin(self, nums: List[int]) -> int:
        length=len(nums)
        if length==1:
            return 1
        minimum=nums[0]
        for i in range(1,length):
            if minimum > nums[i]:
                minimum=nums[i]
            if nums[i] < nums[i-1]:
                return nums[i]
        
        return minimum
```