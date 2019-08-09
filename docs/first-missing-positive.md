---
id: first-missing-positive
title: First Missing Positive
sidebar_label: First Missing Positive
---
## Description
<div class="description">
<p>Given an unsorted integer array, find the smallest missing&nbsp;positive integer.</p>

<p><strong>Example 1:</strong></p>

<pre>
Input: [1,2,0]
Output: 3
</pre>

<p><strong>Example 2:</strong></p>

<pre>
Input: [3,4,-1,1]
Output: 2
</pre>

<p><strong>Example 3:</strong></p>

<pre>
Input: [7,8,9,11,12]
Output: 1
</pre>

<p><strong>Note:</strong></p>

<p>Your algorithm should run in <em>O</em>(<em>n</em>) time and uses constant extra space.</p>

</div>

## Solution(python3)
```python3
class Solution:
    def firstMissingPositive(self, nums: List[int]) -> int:
        
        if len(nums) <= 0:
            return 1
        m=max(nums)
        if m< 0:
            m=1
        nums=set(nums)
        for i in range(1,m+2):
            if i not in nums:
                return i
```