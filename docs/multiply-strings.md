---
id: multiply-strings
title: Multiply Strings
sidebar_label: Multiply Strings
---
## Description
<div class="description">
<p>Given two non-negative integers <code>num1</code> and <code>num2</code> represented as strings, return the product of <code>num1</code> and <code>num2</code>, also represented as a string.</p>

<p><strong>Example 1:</strong></p>

<pre>
<strong>Input:</strong> num1 = &quot;2&quot;, num2 = &quot;3&quot;
<strong>Output:</strong> &quot;6&quot;</pre>

<p><strong>Example 2:</strong></p>

<pre>
<strong>Input:</strong> num1 = &quot;123&quot;, num2 = &quot;456&quot;
<strong>Output:</strong> &quot;56088&quot;
</pre>

<p><strong>Note:</strong></p>

<ol>
	<li>The length of both <code>num1</code> and <code>num2</code> is &lt; 110.</li>
	<li>Both <code>num1</code> and <code>num2</code> contain&nbsp;only digits <code>0-9</code>.</li>
	<li>Both <code>num1</code> and <code>num2</code>&nbsp;do not contain any leading zero, except the number 0 itself.</li>
	<li>You <strong>must not use any built-in BigInteger library</strong> or <strong>convert the inputs to integer</strong> directly.</li>
</ol>

</div>

## Solution(python3)
```python3
class Solution:
    def multiply(self, num1: str, num2: str) -> str:
        number1=0
        x=1
        number2=0    
        for i in num1[::-1]:
            c= ord(i)-48
            number1= number1+c*x
            x=x*10
        x=1
        for j in num2[::-1]:
            d=ord(j)-48
            number2=number2+d*x
            x=x*10
        number3 = number1*number2
        return str(number3)
```