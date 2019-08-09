---
id: majority-element
title: Majority Element
sidebar_label: Majority Element
---
## Description
<div class="description">
<p>Given an array of size <i>n</i>, find the majority element. The majority element is the element that appears <b>more than</b> <code>&lfloor; n/2 &rfloor;</code> times.</p>

<p>You may assume that the array is non-empty and the majority element always exist in the array.</p>

<p><strong>Example 1:</strong></p>

<pre>
<strong>Input:</strong> [3,2,3]
<strong>Output:</strong> 3</pre>

<p><strong>Example 2:</strong></p>

<pre>
<strong>Input:</strong> [2,2,1,1,1,2,2]
<strong>Output:</strong> 2
</pre>

</div>

## Solution(python3)
```python3
class Solution:
    def majorityElement(self, nums: List[int]) -> int:
        diction={}
        
        for i in nums:
            if i not in diction:
                diction[i]=1
            else:
                diction[i]+=1
        returnkrna=0
        maxim=0
        for keys,values in diction.items():
            if values > maxim:
                maxim=values
                returnkrna=keys
        if math.floor(len(nums)/2)<maxim:
            return returnkrna
                
```