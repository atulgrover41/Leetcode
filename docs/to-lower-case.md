---
id: to-lower-case
title: To Lower Case
sidebar_label: To Lower Case
---
## Description
<div class="description">
<p>Implement function ToLowerCase() that has a string parameter str, and returns the same string in lowercase.</p>

<p>&nbsp;</p>

<div>
<p><strong>Example 1:</strong></p>

<pre>
<strong>Input: </strong><span id="example-input-1-1">&quot;Hello&quot;</span>
<strong>Output: </strong><span id="example-output-1">&quot;hello&quot;</span>
</pre>

<div>
<p><strong>Example 2:</strong></p>

<pre>
<strong>Input: </strong><span id="example-input-2-1">&quot;here&quot;</span>
<strong>Output: </strong><span id="example-output-2">&quot;here&quot;</span>
</pre>

<div>
<p><strong>Example 3:</strong></p>

<pre>
<strong>Input: </strong><span id="example-input-3-1">&quot;LOVELY&quot;</span>
<strong>Output: </strong><span id="example-output-3">&quot;lovely&quot;</span>
</pre>
</div>
</div>
</div>

</div>

## Solution(c)
```c
char* toLowerCase(char* str) {
    int i = 0;
    while(str[i]!='\0'){
        if(64<str[i] && str[i]<91)
            str[i] = str[i] +32;
        i++;
    }
    return str;
}
```