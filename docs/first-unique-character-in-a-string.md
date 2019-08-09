---
id: first-unique-character-in-a-string
title: First Unique Character in a String
sidebar_label: First Unique Character in a String
---
## Description
<div class="description">
<p>
Given a string, find the first non-repeating character in it and return it's index. If it doesn't exist, return -1.
</p>
<p><b>Examples:</b>
<pre>
s = "leetcode"
return 0.

s = "loveleetcode",
return 2.
</pre>
</p>

<p>
<b>Note:</b> You may assume the string contain only lowercase letters.
</p>
</div>

## Solution(python)
```python
class Solution(object):
    def firstUniqChar(self, s):
        """
        :type s: str
        :rtype: int
        """
        m=collections.Counter(s)
        for i,j in enumerate(s):
            if m[j] == 1:
                return i
        return -1
```