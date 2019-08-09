---
id: single-element-in-a-sorted-array
title: Single Element in a Sorted Array
sidebar_label: Single Element in a Sorted Array
---
## Description
<div class="description">
<p>Given a sorted array consisting of only integers where every element appears exactly twice except for one element which appears exactly&nbsp;once. Find this single element that appears only once.</p>

<p>&nbsp;</p>

<p><b>Example 1:</b></p>

<pre>
<b>Input:</b> [1,1,2,3,3,4,4,8,8]
<b>Output:</b> 2
</pre>

<p><b>Example 2:</b></p>

<pre>
<b>Input:</b> [3,3,7,7,10,11,11]
<b>Output:</b> 10
</pre>

<p>&nbsp;</p>

<p><b>Note:</b> Your solution should run in O(log n) time and O(1) space.</p>

</div>

## Solution(python)
```python
class Solution(object):
    def singleNonDuplicate(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        nums=collections.Counter(nums)
        i,j=nums.most_common()[-1]
        return i
```