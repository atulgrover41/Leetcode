---
id: map-sum-pairs
title: Map Sum Pairs
sidebar_label: Map Sum Pairs
---
## Description
<div class="description">
<p>
Implement a MapSum class with <code>insert</code>, and <code>sum</code> methods.
</p>

<p>
For the method <code>insert</code>, you'll be given a pair of (string, integer). The string represents the key and the integer represents the value. If the key already existed, then the original key-value pair will be overridden to the new one.
</p>

<p>
For the method <code>sum</code>, you'll be given a string representing the prefix, and you need to return the sum of all the pairs' value whose key starts with the prefix.
</p>

<p><b>Example 1:</b><br />
<pre>
Input: insert("apple", 3), Output: Null
Input: sum("ap"), Output: 3
Input: insert("app", 2), Output: Null
Input: sum("ap"), Output: 5
</pre>
</p>

</div>

## Solution(python)
```python
class MapSum(object):

    def __init__(self):
        """
        Initialize your data structure here.
        """
        self.dic={}

    def insert(self, key, val):
        """
        :type key: str
        :type val: int
        :rtype: None
        """
        self.dic[key]=val
        

    def sum(self, prefix):
        """
        :type prefix: str
        :rtype: int
        """
        newlist=self.dic.keys()
        matching = [s for s in newlist if prefix in s[:len(prefix)]]
        sumo=0
        print(self.dic,prefix,matching)
        while matching:
            sumo+=self.dic[matching.pop(0)]
        return sumo

# Your MapSum object will be instantiated and called as such:
# obj = MapSum()
# obj.insert(key,val)
# param_2 = obj.sum(prefix)
```