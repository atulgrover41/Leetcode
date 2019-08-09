---
id: fizz-buzz
title: Fizz Buzz
sidebar_label: Fizz Buzz
---
## Description
<div class="description">
<p>Write a program that outputs the string representation of numbers from 1 to <i>n</i>.</p>

<p>But for multiples of three it should output “Fizz” instead of the number and for the multiples of five output “Buzz”. For numbers which are multiples of both three and five output “FizzBuzz”.</p>

<p><b>Example:</b>
<pre>
n = 15,

Return:
[
    "1",
    "2",
    "Fizz",
    "4",
    "Buzz",
    "Fizz",
    "7",
    "8",
    "Fizz",
    "Buzz",
    "11",
    "Fizz",
    "13",
    "14",
    "FizzBuzz"
]
</pre>
</p>
</div>

## Solution(python)
```python
class Solution(object):
    def fizzBuzz(self, n):
        """
        :type n: int
        :rtype: List[str]
        """
        returnkr=[]
        for i in range(1,n+1):
            if i % 3 ==0 and i % 5 ==0:
                returnkr.append("FizzBuzz")
            elif i %3 == 0:
                returnkr.append("Fizz")
            elif i%5 == 0:
                returnkr.append("Buzz")
            else:
                returnkr.append(str(i))
        return returnkr
```