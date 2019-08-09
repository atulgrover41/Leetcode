---
id: add-digits
title: Add Digits
sidebar_label: Add Digits
---
## Description
<div class="description">
<p>Given a non-negative integer <code>num</code>, repeatedly add all its digits until the result has only one digit.</p>

<p><strong>Example:</strong></p>

<pre>
<strong>Input:</strong> <code>38</code>
<strong>Output:</strong> 2 
<strong>Explanation: </strong>The process is like: <code>3 + 8 = 11</code>, <code>1 + 1 = 2</code>. 
&nbsp;            Since <code>2</code> has only one digit, return it.
</pre>

<p><b>Follow up:</b><br />
Could you do it without any loop/recursion in O(1) runtime?</p>
</div>

## Solution(python3)
```python3
def sep(n):
    l=[]
    if n ==0:
        return [0]
    while n > 0:
        l.append(n%10)
        n=math.floor(n/10)    
    return l
class Solution:
    def addDigits(self, num: int) -> int:
        number=sep(num)
        while len(number) !=1:
            number=sep(sum(number))
        return number[0]
```