---
id: search-insert-position
title: Search Insert Position
sidebar_label: Search Insert Position
---
## Description
<div class="description">
<p>Given a sorted array and a target value, return the index if the target is found. If not, return the index where it would be if it were inserted in order.</p>

<p>You may assume no duplicates in the array.</p>

<p><strong>Example 1:</strong></p>

<pre>
<strong>Input:</strong> [1,3,5,6], 5
<strong>Output:</strong> 2
</pre>

<p><strong>Example 2:</strong></p>

<pre>
<strong>Input:</strong> [1,3,5,6], 2
<strong>Output:</strong> 1
</pre>

<p><strong>Example 3:</strong></p>

<pre>
<strong>Input:</strong> [1,3,5,6], 7
<strong>Output:</strong> 4
</pre>

<p><strong>Example 4:</strong></p>

<pre>
<strong>Input:</strong> [1,3,5,6], 0
<strong>Output:</strong> 0
</pre>

</div>

## Solution(python3)
```python3
class Solution:
    def searchInsert(self, nums: List[int], target: int) -> int:
        i=0
        n=math.floor(len(nums)/2)
       
        if nums[n] <= target:
            i=n
       
        while i < len(nums) and nums[i]<= target:
            if nums[i] == target:
                return i
            i=i+1
        return i    
```