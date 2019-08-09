---
id: self-dividing-numbers
title: Self Dividing Numbers
sidebar_label: Self Dividing Numbers
---
## Description
<div class="description">
<p>
A <i>self-dividing number</i> is a number that is divisible by every digit it contains.
</p><p>
For example, 128 is a self-dividing number because <code>128 % 1 == 0</code>, <code>128 % 2 == 0</code>, and <code>128 % 8 == 0</code>.
</p><p>
Also, a self-dividing number is not allowed to contain the digit zero.
</p><p>
Given a lower and upper number bound, output a list of every possible self dividing number, including the bounds if possible.
</p>
<p><b>Example 1:</b><br />
<pre>
<b>Input:</b> 
left = 1, right = 22
<b>Output:</b> [1, 2, 3, 4, 5, 6, 7, 8, 9, 11, 12, 15, 22]
</pre>
</p>

<p><b>Note:</b>
<li>The boundaries of each input argument are <code>1 <= left <= right <= 10000</code>.</li>
</p>
</div>

## Solution(python)
```python
class Solution(object):
    
    def sep(self,n):
        l=[]
        while n > 0:
            l.append(n%10)
            if l[-1] ==0:
                return False
            n=n/10
        return l
        
    def check(self,n,m):
        k=[]
        for i in m:
            if n % i ==0:
                k.append(True)
        return k
    
    def selfDividingNumbers(self, left, right):
        """
        :type left: int
        :type right: int
        :rtype: List[int]
        """
        l=[]
        for i in range(left,right+1):
            if self.sep(i) is not False:
                m=self.sep(i)
                if len(self.check(i,m)) ==len(m):
                    l.append(i)
        return l
                    
```