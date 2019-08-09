---
id: maximum-product-of-three-numbers
title: Maximum Product of Three Numbers
sidebar_label: Maximum Product of Three Numbers
---
## Description
<div class="description">
<p>Given an integer array, find three numbers whose product is maximum and output the maximum product.</p>

<p><b>Example 1:</b></p>

<pre>
<b>Input:</b> [1,2,3]
<b>Output:</b> 6
</pre>

<p>&nbsp;</p>

<p><b>Example 2:</b></p>

<pre>
<b>Input:</b> [1,2,3,4]
<b>Output:</b> 24
</pre>

<p>&nbsp;</p>

<p><b>Note:</b></p>

<ol>
	<li>The length of the given array will be in range [3,10<sup>4</sup>] and all elements are in the range [-1000, 1000].</li>
	<li>Multiplication of any three numbers in the input won&#39;t exceed the range of 32-bit signed integer.</li>
</ol>

<p>&nbsp;</p>

</div>

## Solution(python)
```python
class Solution(object):
    def maximumProduct(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        nums=sorted(nums)
        return max(nums[-1]*nums[-2]*nums[-3],nums[-1]*nums[0]*nums[1])
```