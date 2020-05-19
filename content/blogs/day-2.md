+++
title = "Happy number: Day 2 of the 30 days coding challenge"
description = ""
type = ["blogs","blog"]
tags = [
    "Competitive Coding",
    "Competitive Programming",
    "Algorithms",
    "Data Structures",
]
date = "2020-04-17"
categories = [
    "Competitive Coding",
    "Algorithms",
    "Data Structures",
]
series = ["Competitive Coding"]
[ author ]
  name = "Vidhi Mody"
+++
> *“Perfection is achieved not when there is nothing more to add, but rather when there is nothing more to take away.”* \
> ~Antoine de Saint-Exupery


Day 2 of the [30 days coding challenge](https://leetcode.com/explore/challenge/card/30-day-leetcoding-challenge/) by [Leetcode](https://leetcode.com/)

I thought it would be a good idea to attempt another problem today itself since the challenge started on April 1 and I'm running late already!

### Problem definition: Happy number 

Write an algorithm to determine if a number `n` is "happy". 

A happy number is a number defined by the following process: Starting with any positive integer, replace the number by the sum of the squares of its digits, and repeat the process until the number equals 1 (where it will stay), or it loops endlessly in a cycle which does not include 1. Those numbers for which this process ends in 1 are happy numbers.

Return **True** if `n` is a **happy number**, and False if not.

#### Sample Testcase 

Testcase 1
```
Input: 19
Output: true
```
>Explanation: \
1^2 + 9^2 = 82 \
8^2 + 2^2 = 68 \
6^2 + 8^2 = 100 \
1^2 + 0^2 + 0^2 = 1

I highly encourage you to attempt this problem on your own before looking at my solution.

## Solution

```python
class Solution:
    def isHappy(self, n: int) -> bool:
        count=0
        while(True):
            str1=str(n)
            temp=0
            for i in range(0,len(str1)):
                temp=temp+(int(str1[i])*int(str1[i]))
            if(n == temp or n<temp):
                count = count+1
            elif(n>temp):
                count = count - 1
            n=temp
            if(n==1):
                return True
            elif(count>4):
                return False
```

### Submission Details

**Total test cases passed**: 401/401 \
**Runtime**: 40 ms \
**Memory Usage**:13.6 MB 

>Note: This submission was better than 11.33% of Python3 solutions in terms of runtime. Therefore a better approach to reduce the time complexity can be thought of!:new_moon_with_face:

I would really recommend you to explore this side of the Computer Science and tune in to the journey of competitive programming to write better, cleaner, efficient and optimal code! :grinning:

If you have a better approach to this problem, or for any other queries feel free to reach out to [me]((https://www.linkedin.com/in/vidhi-mody-21629a150))! :innocent:



