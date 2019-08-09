---
id: detect-capital
title: Detect Capital
sidebar_label: Detect Capital
---
## Description
<div class="description">
<p>Given a word, you need to judge whether the usage of capitals in it is right or not.</p>

<p>We define the usage of capitals in a word to be right when one of the following cases holds:</p>

<ol>
	<li>All letters in this word are capitals, like &quot;USA&quot;.</li>
	<li>All letters in this word are not capitals, like &quot;leetcode&quot;.</li>
	<li>Only the first letter in this word is capital, like &quot;Google&quot;.</li>
</ol>
Otherwise, we define that this word doesn&#39;t use capitals in a right way.

<p>&nbsp;</p>

<p><b>Example 1:</b></p>

<pre>
<b>Input:</b> &quot;USA&quot;
<b>Output:</b> True
</pre>

<p>&nbsp;</p>

<p><b>Example 2:</b></p>

<pre>
<b>Input:</b> &quot;FlaG&quot;
<b>Output:</b> False
</pre>

<p>&nbsp;</p>

<p><b>Note:</b> The input will be a non-empty word consisting of uppercase and lowercase latin letters.</p>

</div>

## Solution(python3)
```python3
class Solution:
    def detectCapitalUse(self, word: str) -> bool:
        text=0
        if len(word) <=1:
            return True
        if word.isupper() != True:
            if word[1:].islower():
                return True
            else:
                return False
       
        return True
```