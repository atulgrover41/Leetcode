---
id: happy-number
title: Happy Number
sidebar_label: Happy Number
---
## Description
<div class="description">
<p>Write an algorithm to determine if a number is &quot;happy&quot;.</p>

<p>A happy number is a number defined by the following process: Starting with any positive integer, replace the number by the sum of the squares of its digits, and repeat the process until the number equals 1 (where it will stay), or it loops endlessly in a cycle which does not include 1. Those numbers for which this process ends in 1 are happy numbers.</p>

<p><strong>Example:&nbsp;</strong></p>

<pre>
<strong>Input:</strong> 19
<strong>Output:</strong> true
<strong>Explanation: 
</strong>1<sup>2</sup> + 9<sup>2</sup> = 82
8<sup>2</sup> + 2<sup>2</sup> = 68
6<sup>2</sup> + 8<sup>2</sup> = 100
1<sup>2</sup> + 0<sup>2</sup> + 0<sup>2</sup> = 1
</pre>
</div>

## Solution(python3)
```python3
def sep(n):
    l=[]
    while n > 0:
        l.append(n%10)
        n=math.floor(n/10)    
    return l
class Solution:
    def isHappy(self, n: int) -> bool:
        number = sep(n)
        z=0
        while sum(number) != 1:
            m=0
            z+=1
            for i in number:
                m+=pow(i,2)
            if z >10:
                return False
            number=sep(m)
        return True
```