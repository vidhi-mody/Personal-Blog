+++
title = "Valid Perfect Square: Day 9 of the May LeetCoding Challenge"
description = ""
type = ["blogs","blog"]
tags = [
    "Competitive Coding",
    "Competitive Programming",
    "Algorithms",
    "Data Structures",
]
date = "2020-05-10"
categories = [
    "Competitive Coding",
    "Algorithms",
    "Data Structures",
]
series = ["Competitive Coding"]
[ author ]
  name = "Vidhi Mody"
+++

> *“First solve the problem. Then, write the code.”*

Day 9 of the [May LeetCoding Challenge](https://leetcode.com/explore/featured/card/may-leetcoding-challenge/) by [Leetcode](https://leetcode.com/)

The lockdown has caused you to be confined at home. Boredom is sure to kick in soon. Keep all distractions aside, rather than streaming yet another web series, do something positive to uplift yourself. Learning a new skill can give you the much needed social detox! As our skill increases, so does the challenge. *"When we’re in flow, the level of challenge in the activity just exceeds our level of skill."*


### Problem definition: Valid Perfect Square

Given a positive integer *num*, write a function which returns True if *num* is a perfect square else False.

> **Note**: \
> **Do not** use any built-in library function such as `sqrt`.

#### Sample Testcase 

Testcase 1

```
Input: 16
Output: true
```

Testcase 2

```
Input: 14
Output: false
```

I highly encourage you to attempt this [problem](https://leetcode.com/explore/challenge/card/may-leetcoding-challenge/535/week-2-may-8th-may-14th/) on your own before looking at my solution.

## Approach 1

If the input number if 1 return `True` or starting from 2, keep incrementing the number until it's square value becomes greater than the input number. \
It will yield a time complexity of `O(sqrt(n))`

## Solution

```python
class Solution:
    def isPerfectSquare(self, num: int) -> bool:
        if(num<=1):
            return True
        else:
            i=2
            while(i*i<=num):
                if(i*i==num):
                    return True
                else:
                    i=i+1
```

## Approach 2

I was able to come up with a better approack for the given problem. [Binary Search](https://www.geeksforgeeks.org/binary-search/) can be used to locate the square root of the given element. (if it exists) \
Time Complexity: `O(log(n))`

## Solution

```python
def isSquare(start,end,num):
    while(start<=end):
        mid = start + (end-start)//2
        if(mid*mid==num):
            return True
        elif(mid*mid > num):
            end = mid - 1
        else:
            start = k=mid + 1
    return False
        

class Solution:
    def isPerfectSquare(self, num: int) -> bool:
        if(num<=1):
            return True
        else:
            ans = isSquare(2,num,num)
            return ans
```

### Submission Details

**Total test cases passed**: 68 / 68 \
**Runtime**: 20 ms \
**Memory Usage**: 13.8 MB 

>Note: This submission was better than 98.25% of Python3 solutions in terms of runtime! :new_moon_with_face: 

{{<center src="/img/happy.gif" alt="Happy">}}

I would really recommend you to explore this side of the Computer Science and tune in to the journey of competitive programming to write better, cleaner, efficient and optimal code! :grinning:

If you have a better approach to this problem, or for any other queries feel free to reach out to [me]((https://www.linkedin.com/in/vidhi-mody-21629a150))! :innocent:
