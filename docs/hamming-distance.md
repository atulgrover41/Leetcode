---
id: hamming-distance
title: Hamming Distance
sidebar_label: Hamming Distance
---
## Description
<div class="description">
<p>The <a href="https://en.wikipedia.org/wiki/Hamming_distance" target="_blank">Hamming distance</a> between two integers is the number of positions at which the corresponding bits are different.</p>

<p>Given two integers <code>x</code> and <code>y</code>, calculate the Hamming distance.</p>

<p><b>Note:</b><br />
0 &le; <code>x</code>, <code>y</code> &lt; 2<sup>31</sup>.
</p>

<p><b>Example:</b>
<pre>
<b>Input:</b> x = 1, y = 4

<b>Output:</b> 2

<b>Explanation:</b>
1   (0 0 0 1)
4   (0 1 0 0)
       &uarr;   &uarr;

The above arrows point to positions where the corresponding bits are different.
</pre>
</p>
</div>

## Solution(python)
```python
class Solution(object):
    def hammingDistance(self, x, y):
        """
        :type x: int
        :type y: int
        :rtype: int
        """
        x=format(x,'032b')
        y=format(y,'032b')
        sumo=0
        #print(x,y)
        for i,j in zip(x,y):
            if i!=j:
                sumo+=1
        return sumo
        
```