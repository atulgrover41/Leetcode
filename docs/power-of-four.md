---
id: power-of-four
title: Power of Four
sidebar_label: Power of Four
---
## Description
<div class="description">
<p>Given an integer (signed 32 bits), write a function to check whether it is a power of 4.</p>

<p><strong>Example 1:</strong></p>

<pre>
<strong>Input: </strong><span id="example-input-1-1">16</span>
<strong>Output: </strong><span id="example-output-1">true</span>
</pre>

<div>
<p><strong>Example 2:</strong></p>

<pre>
<strong>Input: </strong><span id="example-input-2-1">5</span>
<strong>Output: </strong><span id="example-output-2">false</span></pre>
</div>

<p><b>Follow up</b>: Could you solve it without loops/recursion?</p>
</div>

## Solution(python)
```python
class Solution(object):
    def isPowerOfFour(self, num):
        if num <= 0:
            return False
        m=1
        y= math.log(num,4)
        if y.is_integer():
            return True
        return False
```