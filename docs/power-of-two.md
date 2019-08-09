---
id: power-of-two
title: Power of Two
sidebar_label: Power of Two
---
## Description
<div class="description">
<p>Given an integer, write a function to determine if it is a power of two.</p>

<p><strong>Example 1:</strong></p>

<pre>
<strong>Input:</strong> 1
<strong>Output:</strong> true 
<strong>Explanation: </strong>2<sup>0</sup>&nbsp;= 1
</pre>

<p><strong>Example 2:</strong></p>

<pre>
<strong>Input:</strong> 16
<strong>Output:</strong> true
<strong>Explanation: </strong>2<sup>4</sup>&nbsp;= 16</pre>

<p><strong>Example 3:</strong></p>

<pre>
<strong>Input:</strong> 218
<strong>Output:</strong> false</pre>

</div>

## Solution(python)
```python
def truncate(number, digits):
    stepper = pow(10.0, digits)
    return math.trunc(stepper * number) / stepper

class Solution(object):
    def isPowerOfTwo(self, n):
        """
        :type n: int
        :rtype: bool
        """
        if n<= 0:
            return False
        x=math.log(n,2)
        x= truncate(x,12)
        if x.is_integer():
            return True
        
        return False
```