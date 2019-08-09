---
id: sort-array-by-parity
title: Sort Array By Parity
sidebar_label: Sort Array By Parity
---
## Description
<div class="description">
<p>Given an array <code>A</code> of non-negative integers, return an array consisting of all the even elements of <code>A</code>, followed by all the odd elements of <code>A</code>.</p>

<p>You may return any answer array that satisfies this condition.</p>

<p>&nbsp;</p>

<div>
<p><strong>Example 1:</strong></p>

<pre>
<strong>Input: </strong><span id="example-input-1-1">[3,1,2,4]</span>
<strong>Output: </strong><span id="example-output-1">[2,4,3,1]</span>
The outputs [4,2,3,1], [2,4,1,3], and [4,2,1,3] would also be accepted.
</pre>

<p>&nbsp;</p>

<p><strong>Note:</strong></p>

<ol>
	<li><code>1 &lt;= A.length &lt;= 5000</code></li>
	<li><code>0 &lt;= A[i] &lt;= 5000</code></li>
</ol>
</div>

</div>

## Solution(c)
```c
/**
 * Return an array of size *returnSize.
 * Note: The returned array must be malloced, assume caller calls free().
 */
int* sortArrayByParity(int* A, int ASize, int* returnSize) {
    int array2[ASize],k=0,m=0,i;
    int *array1=(int *)calloc(ASize,sizeof(int));
    for(i=0;i<ASize;i++){
        if(A[i]%2==0){array1[m]=A[i];
                     m++;}
        else{array2[k]=A[i];
            k++;}
    }
    k=0;
    for(i=m;i<ASize;i++){
        array1[i]=array2[k];
        //printf("%d \t",array1[i]);
        k++;
    }
    
    *returnSize=ASize;
    return array1;
}
```