---
id: product-of-array-except-self
title: Product of Array Except Self
sidebar_label: Product of Array Except Self
---
## Description
<div class="description">
<p>Given an array <code>nums</code> of <em>n</em> integers where <em>n</em> &gt; 1, &nbsp;return an array <code>output</code> such that <code>output[i]</code> is equal to the product of all the elements of <code>nums</code> except <code>nums[i]</code>.</p>

<p><b>Example:</b></p>

<pre>
<b>Input:</b>  <code>[1,2,3,4]</code>
<b>Output:</b> <code>[24,12,8,6]</code>
</pre>

<p><strong>Note: </strong>Please solve it <strong>without division</strong> and in O(<em>n</em>).</p>

<p><strong>Follow up:</strong><br />
Could you solve it with constant space complexity? (The output array <strong>does not</strong> count as extra space for the purpose of space complexity analysis.)</p>

</div>

## Solution(python3)
```python3
class Solution:
    def productExceptSelf(self, nums: List[int]) -> List[int]:
        mul=1
        l=[]
        for i in nums:
            mul*=i
        zeromul=1
        for i in enumerate(nums):
            if i[1] != 0:
                l.append(int(mul/i[1]))
            else:
                zeromul=1
                for j in enumerate(nums):
                    if j[0]!=i[0]:
                        zeromul *=j[1]
                l.append(zeromul)
        return l
```