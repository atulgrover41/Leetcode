---
id: positions-of-large-groups
title: Positions of Large Groups
sidebar_label: Positions of Large Groups
---
## Description
<div class="description">
<p>In a string&nbsp;<code>S</code>&nbsp;of lowercase letters, these letters form consecutive groups of the same character.</p>

<p>For example, a string like <code>S = &quot;abbxxxxzyy&quot;</code> has the groups <code>&quot;a&quot;</code>, <code>&quot;bb&quot;</code>, <code>&quot;xxxx&quot;</code>, <code>&quot;z&quot;</code> and&nbsp;<code>&quot;yy&quot;</code>.</p>

<p>Call a group <em>large</em> if it has 3 or more characters.&nbsp; We would like the starting and ending positions of every large group.</p>

<p>The final answer should be in lexicographic order.</p>

<p>&nbsp;</p>

<p><strong>Example 1:</strong></p>

<pre>
<strong>Input: </strong>&quot;abbxxxxzzy&quot;
<strong>Output: </strong>[[3,6]]
<strong>Explanation</strong>: <code>&quot;xxxx&quot; is the single </code>large group with starting  3 and ending positions 6.
</pre>

<p><strong>Example 2:</strong></p>

<pre>
<strong>Input: </strong>&quot;abc&quot;
<strong>Output: </strong>[]
<strong>Explanation</strong>: We have &quot;a&quot;,&quot;b&quot; and &quot;c&quot; but no large group.
</pre>

<p><strong>Example 3:</strong></p>

<pre>
<strong>Input: </strong>&quot;abcdddeeeeaabbbcd&quot;
<strong>Output: </strong>[[3,5],[6,9],[12,14]]</pre>

<p>&nbsp;</p>

<p><strong>Note:&nbsp;</strong>&nbsp;<code>1 &lt;= S.length &lt;= 1000</code></p>

</div>

## Solution(python3)
```python3
class Solution:
    def largeGroupPositions(self, S: str) -> List[List[int]]:
        x=[0,S[0],0,1]
        ret=[]
        for i,j in enumerate(S):
            
            if x[1] != j and x[0] <3:
                x[3]=i
                x[2] = x[3]
                x[0]=1
                x[1]=j
                
            elif x[1] != j and x[0] >=3:
                
                x[1]= j
                ret.append([x[2],x[3]])
                x[0]=1
                x[3]=i
                x[2]=x[3]

            else:
                x[0]+=1
                x[3] =i
        
        if x[0] >= 3:
            ret.append([x[2],x[3]])
        
        return ret
            
```