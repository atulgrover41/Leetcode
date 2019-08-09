---
id: palindrome-number
title: Palindrome Number
sidebar_label: Palindrome Number
---
## Description
<div class="description">
<p>Determine whether an integer is a palindrome. An integer&nbsp;is&nbsp;a&nbsp;palindrome when it&nbsp;reads the same backward as forward.</p>

<p><strong>Example 1:</strong></p>

<pre>
<strong>Input:</strong> 121
<strong>Output:</strong> true
</pre>

<p><strong>Example 2:</strong></p>

<pre>
<strong>Input:</strong> -121
<strong>Output:</strong> false
<strong>Explanation:</strong> From left to right, it reads -121. From right to left, it becomes 121-. Therefore it is not a palindrome.
</pre>

<p><strong>Example 3:</strong></p>

<pre>
<strong>Input:</strong> 10
<strong>Output:</strong> false
<strong>Explanation:</strong> Reads 01 from right to left. Therefore it is not a palindrome.
</pre>

<p><strong>Follow up:</strong></p>

<p>Coud you solve&nbsp;it without converting the integer to a string?</p>

</div>

## Solution(python3)
```python3
class Solution:
    def isPalindrome(self, x: int) -> bool:
        if x < 0:
            return False
        m=x
        l=[]
        while m > 0:
            l.append(m %10)
            m=int(m/10)
        newlist=copy.copy(l)
        newlist.reverse()
        for i,j in zip(l,newlist):
            if i != j:
                return False
        return True
            
```