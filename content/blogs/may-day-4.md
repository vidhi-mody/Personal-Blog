+++
title = "Number Complement: Day 4 of the May LeetCoding Challenge"
description = ""
type = ["blogs","blog"]
tags = [
    "Competitive Coding",
    "Competitive Programming",
    "Algorithms",
    "Data Structures",
]
date = "2020-05-05"
categories = [
    "Competitive Coding",
    "Algorithms",
    "Data Structures",
]
series = ["Competitive Coding"]
[ author ]
  name = "Vidhi Mody"
+++
> *“The best thing about a boolean is even if you are wrong, you are only off by a bit.”*\
> ~Bryan


Day 4 of the [May LeetCoding Challenge](https://leetcode.com/explore/featured/card/may-leetcoding-challenge/) by [Leetcode](https://leetcode.com/)

When you start out with competitive coding, you may tend to set unreasonable goals for yourself. The problem with this is that it cannot be achieved overnight. Start with the basics, you may take time to understand stuff, but that's okay! Work on a few problems daily and you are sure to see the difference. *And practice makes perfect, right?*

### Problem definition: Number Complement

Given a positive integer, output its complement number. The complement strategy is to flip the bits of its binary representation.

> Note:
> - The given integer is guaranteed to fit within the range of a 32-bit signed integer.
> - You could assume no leading zero bit in the integer’s binary representation.
> - This question is the same as [1009](https://leetcode.com/problems/complement-of-base-10-integer/)

#### Sample Testcase 

Testcase 1
```
Input: 5
Output: 2
Explanation: The binary representation of 5 is 101 (no leading zero bits), and its complement is 010.
So you need to output 2.
```

Testcase 2
```
Input: 1
Output: 0
Explanation: The binary representation of 1 is 1 (no leading zero bits), and its complement is 0.
So you need to output 0.
```

I highly encourage you to attempt this [problem](https://leetcode.com/explore/featured/card/may-leetcoding-challenge/534/week-1-may-1st-may-7th/) on your own before looking at my solution.

## Approach

The NOT bitwise operator in could be one approach to solving the problem. To implement everything from scrath you can convert the decimal to binary, complement it and return the decimal of the binary number obtained!

## Solution

```python
class Solution(object):
    def findComplement(self, num):
        """
        :type num: int
        :rtype: int
        """
        ones = ""
        binary = bin(num)
        binary = binary.replace('0b','')
        for i in range(0,len(binary)):
            if(binary[i]=='0'):
                ones = ones + '1'
            else:
                ones = ones + '0'
        return int(ones,2)   
```

### Submission Details

**Total test cases passed**: 149 / 149 \
**Runtime**: 20 ms \
**Memory Usage**: 12.6 MB 

>Note: This submission was better than 43.98% of Python3 solutions in terms of runtime. Think hard and try to come up with a solution that is more optimal! :new_moon_with_face: \
You could use Bitwise operators as an alternative! 

I would really recommend you to explore this side of the Computer Science and tune in to the journey of competitive programming to write better, cleaner, efficient and optimal code! :grinning:

If you have a better approach to this problem, or for any other queries feel free to reach out to [me]((https://www.linkedin.com/in/vidhi-mody-21629a150))! :innocent:
