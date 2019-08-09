---
id: pascals-triangle
title: Pascal's Triangle
sidebar_label: Pascal's Triangle
---
## Description
<div class="description">
<p>Given a non-negative integer&nbsp;<em>numRows</em>, generate the first <em>numRows</em> of Pascal&#39;s triangle.</p>

<p><img alt="" src="https://upload.wikimedia.org/wikipedia/commons/0/0d/PascalTriangleAnimated2.gif" style="height:240px; width:260px" /><br />
<small>In Pascal&#39;s triangle, each number is the sum of the two numbers directly above it.</small></p>

<p><strong>Example:</strong></p>

<pre>
<strong>Input:</strong> 5
<strong>Output:</strong>
[
     [1],
    [1,1],
   [1,2,1],
  [1,3,3,1],
 [1,4,6,4,1]
]
</pre>

</div>

## Solution(python3)
```python3
class Solution:
    def generate(self, numRows: int) -> List[List[int]]:
        triangle =[]
        
        for row_num in range(numRows):
            row = [None for _ in range(row_num +1)]
            row[0], row[-1] = 1, 1
            print(row)
            for j in range(1, len(row)-1):
                row[j]= triangle[row_num-1][j-1] + triangle[row_num-1][j]
            triangle.append(row)
        return triangle
```