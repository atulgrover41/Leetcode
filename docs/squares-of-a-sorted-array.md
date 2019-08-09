---
id: squares-of-a-sorted-array
title: Squares of a Sorted Array
sidebar_label: Squares of a Sorted Array
---
## Description
<div class="description">
<p>Given an array of integers <code>A</code>&nbsp;sorted in non-decreasing order,&nbsp;return an array of the squares of each number,&nbsp;also in sorted non-decreasing order.</p>

<p>&nbsp;</p>

<div>
<p><strong>Example 1:</strong></p>

<pre>
<strong>Input: </strong><span id="example-input-1-1">[-4,-1,0,3,10]</span>
<strong>Output: </strong><span id="example-output-1">[0,1,9,16,100]</span>
</pre>

<div>
<p><strong>Example 2:</strong></p>

<pre>
<strong>Input: </strong><span id="example-input-2-1">[-7,-3,2,3,11]</span>
<strong>Output: </strong><span id="example-output-2">[4,9,9,49,121]</span>
</pre>

<p>&nbsp;</p>

<p><strong><span>Note:</span></strong></p>

<ol>
	<li><code><span>1 &lt;= A.length &lt;= 10000</span></code></li>
	<li><code>-10000 &lt;= A[i] &lt;= 10000</code></li>
	<li><code>A</code>&nbsp;is sorted in non-decreasing order.</li>
</ol>
</div>
</div>
</div>

## Solution(c)
```c
/**
 * Return an array of size *returnSize.
 * Note: The returned array must be malloced, assume caller calls free().
 */
int* sortedSquares(int* A, int ASize, int* returnSize) {
    int i,c,d,swap;
     int *array1=(int *)calloc(ASize,sizeof(int));
    for(i=0;i<ASize;i++){
        A[i]=A[i]*A[i];
        //printf("%d \t",A[i] );
    }
    for (c = 0 ; c < ASize; c++)
  {
    for (d = c+1 ; d < ASize ; d++)
    {
      if (A[c] > A[d]) /* For decreasing order use < */
      {
        swap       = A[d];
        A[d]   = A[c];
        A[c] = swap;
      }
    }   array1[c]= A[c];
        printf("%d \n",array1[c]);
  }
    *returnSize=ASize;
    return array1;
}

```