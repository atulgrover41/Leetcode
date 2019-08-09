---
id: jewels-and-stones
title: Jewels and Stones
sidebar_label: Jewels and Stones
---
## Description
<div class="description">
<p>You&#39;re given strings <code>J</code> representing the types of stones that are jewels, and <code>S</code> representing the stones you have.&nbsp; Each character in <code>S</code> is a type of stone you have.&nbsp; You want to know how many of the stones you have are also jewels.</p>

<p>The letters in <code>J</code> are guaranteed distinct, and all characters in <code>J</code> and <code>S</code> are letters. Letters are case sensitive, so <code>&quot;a&quot;</code> is considered a different type of stone from <code>&quot;A&quot;</code>.</p>

<p><strong>Example 1:</strong></p>

<pre>
<strong>Input:</strong> J = &quot;aA&quot;, S = &quot;aAAbbbb&quot;
<strong>Output:</strong> 3
</pre>

<p><strong>Example 2:</strong></p>

<pre>
<strong>Input:</strong> J = &quot;z&quot;, S = &quot;ZZ&quot;
<strong>Output:</strong> 0
</pre>

<p><strong>Note:</strong></p>

<ul>
	<li><code>S</code> and <code>J</code> will consist of letters and have length at most 50.</li>
	<li>The characters in <code>J</code> are distinct.</li>
</ul>

</div>

## Solution(c)
```c
int numJewelsInStones(char* J, char* S) {
    int i,j,op=0;
    for(i=0;i<strlen(S);i++){
        for(j=0;j<strlen(J);j++){
            if(S[i] == J[j]){
                op+=1;
            break;
            }
        }
    }
    return op;
}
```