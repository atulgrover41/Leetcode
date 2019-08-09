---
id: two-sum
title: Two Sum
sidebar_label: Two Sum
---
## Description
<div class="description">
<p>Given an array of integers, return <strong>indices</strong> of the two numbers such that they add up to a specific target.</p>

<p>You may assume that each input would have <strong><em>exactly</em></strong> one solution, and you may not use the <em>same</em> element twice.</p>

<p><strong>Example:</strong></p>

<pre>
Given nums = [2, 7, 11, 15], target = 9,

Because nums[<strong>0</strong>] + nums[<strong>1</strong>] = 2 + 7 = 9,
return [<strong>0</strong>, <strong>1</strong>].
</pre>

</div>

## Solution(python3)
```python3
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        for i in enumerate(nums):
            newlist=copy.copy(nums)
            newlist.pop(i[0])
            remain = target - i[1]
            for j in enumerate(newlist):
                if j[1] == remain:
                    if j[0] >= i[0]:
                        return i[0],j[0]+1
                    else:
                        return i[0],j[0]
                    
```