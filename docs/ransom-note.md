---
id: ransom-note
title: Ransom Note
sidebar_label: Ransom Note
---
## Description
<div class="description">
<p>
Given an arbitrary ransom note string and another string containing letters from all the magazines, write a function that will return true if the ransom 
note can be constructed from the magazines ; otherwise, it will return false. 
</p>
<p>
Each letter in the magazine string can only be used once in your ransom note.
</p>

<p><b>Note:</b><br />
You may assume that both strings contain only lowercase letters.
</p>

<pre>
canConstruct("a", "b") -> false
canConstruct("aa", "ab") -> false
canConstruct("aa", "aab") -> true
</pre>

</div>

## Solution(python)
```python
class Solution(object):
    def canConstruct(self, ransomNote, magazine):
        """
        :type ransomNote: str
        :type magazine: str
        :rtype: bool
        """
        m=magazine
        for i in ransomNote:
            m=m.replace(i,"",1)
        if (len(magazine)- len(ransomNote)) == len(m):
            return True
        return False
```