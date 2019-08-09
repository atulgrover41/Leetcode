---
id: find-all-numbers-disappeared-in-an-array
title: Find All Numbers Disappeared in an Array
sidebar_label: Find All Numbers Disappeared in an Array
---
## Description
<div class="description">
<p>Given an array of integers where 1 &le; a[i] &le; <i>n</i> (<i>n</i> = size of array), some elements appear twice and others appear once.</p>

<p>Find all the elements of [1, <i>n</i>] inclusive that do not appear in this array.</p>

<p>Could you do it without extra space and in O(<i>n</i>) runtime? You may assume the returned list does not count as extra space.</p>

<p><b>Example:</b>
<pre>
<b>Input:</b>
[4,3,2,7,8,2,3,1]

<b>Output:</b>
[5,6]
</pre>
</p>
</div>

## Solution(python3)
```python3
class Solution:
    def findDisappearedNumbers(self, nums: List[int]) -> List[int]:
        x=len(nums)
        nums=set(nums)
        
        for i in range(1,x+1):
            try:
                nums.remove(i)
            except:
                nums.add(i)
            #print(nums)
        nums=list(nums)
        return nums
```