---
id: arranging-coins
title: Arranging Coins
sidebar_label: Arranging Coins
---
## Description
<div class="description">
<p>You have a total of <i>n</i> coins that you want to form in a staircase shape, where every <i>k</i>-th row must have exactly <i>k</i> coins.</p>
 
<p>Given <i>n</i>, find the total number of <b>full</b> staircase rows that can be formed.</p>

<p><i>n</i> is a non-negative integer and fits within the range of a 32-bit signed integer.</p>

<p><b>Example 1:</b>
<pre>
n = 5

The coins can form the following rows:
¤
¤ ¤
¤ ¤

Because the 3rd row is incomplete, we return 2.
</pre>
</p>

<p><b>Example 2:</b>
<pre>
n = 8

The coins can form the following rows:
¤
¤ ¤
¤ ¤ ¤
¤ ¤

Because the 4th row is incomplete, we return 3.
</pre>
</p>
</div>

## Solution(c)
```c
int arrangeCoins(int n) {
    int i=1,count=0;
    unsigned int diff =n ;
    while(diff>=i){
        diff=diff-i;
        i+=1;
        count+=1;
    }
    return count;
}
```