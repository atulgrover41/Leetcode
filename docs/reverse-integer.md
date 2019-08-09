---
id: reverse-integer
title: Reverse Integer
sidebar_label: Reverse Integer
---
## Description
<div class="description">
<p>Given a 32-bit signed integer, reverse digits of an integer.</p>

<p><strong>Example 1:</strong></p>

<pre>
<strong>Input:</strong> 123
<strong>Output:</strong> 321
</pre>

<p><strong>Example 2:</strong></p>

<pre>
<strong>Input:</strong> -123
<strong>Output:</strong> -321
</pre>

<p><strong>Example 3:</strong></p>

<pre>
<strong>Input:</strong> 120
<strong>Output:</strong> 21
</pre>

<p><strong>Note:</strong><br />
Assume we are dealing with an environment which could only store integers within the 32-bit signed integer range: [&minus;2<sup>31</sup>,&nbsp; 2<sup>31&nbsp;</sup>&minus; 1]. For the purpose of this problem, assume that your function returns 0 when the reversed integer overflows.</p>

</div>

## Solution(python3)
```python3
class Solution:
    def reverse(self, x: int) -> int:
        i=0
        print(pow(2,31))
        if abs(x) > (pow(2,31)):
            return 0
        l=[]
        neg=0
        if x < 0:
            neg=True
            x=abs(x)
        y=x/10
        zero=0
        while(x > 0):
            y=int(x%10)
            x=int(x/10)
            if y != 0 or zero != 0 :
                l.append(y)
                zero+=1
        m=1
        num=0
        for i in l:
            num = num+ i*pow(10,(len(l)-m))
            m=m+1
        if num > pow(2,31):
            return 0
        if neg is True:
            return -num
        return num
```