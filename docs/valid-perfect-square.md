---
id: valid-perfect-square
title: Valid Perfect Square
sidebar_label: Valid Perfect Square
---
## Description
<div class="description">
<p>Given a positive integer <i>num</i>, write a function which returns True if <i>num</i> is a perfect square else False.</p>

<p><b>Note:</b> <b>Do not</b> use any built-in library function such as <code>sqrt</code>.</p>

<p><strong>Example 1:</strong></p>

<div>
<pre>
<strong>Input: </strong><span id="example-input-1-1">16</span>
<strong>Output: </strong><span id="example-output-1">true</span>
</pre>

<div>
<p><strong>Example 2:</strong></p>

<pre>
<strong>Input: </strong><span id="example-input-2-1">14</span>
<strong>Output: </strong><span id="example-output-2">false</span>
</pre>
</div>
</div>
</div>

## Solution(python)
```python
class Solution(object):
    def isPerfectSquare(self, num):
        """
        :type num: int
        :rtype: bool
        """
        if num %10 == 7 or num %10 == 3 or num %10 ==8:
            return False
        n=0
        while(n <= math.ceil(num/2)):

            n+=1
            x=float(num)/n
            if x == n:

                return True
        return False
```