+++
title = "Single number: Day 1 of the 30 days coding challenge"
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
> *"No matter how advanced they become, experts never lose sight of the fundamentals. In many ways, they are advanced for that very reason: they understand the fundamentals better than anyone else."* \
> ~James Clear

Competitive Programming is a continuous cycle of coding, endless debugging, and facing a few failures till you finally succeed! A few reasons why competitive programming is highly beneficial are:
- It enhances your problem solving and debugging skills
- It helps you write cleaner and optimal code 
- It improves your fundamentals
- It helps you showcase your skills
- It prepares you for technical interviews

To brush up my knowledge of data structures and algorithms I decided to take part in the [30 days coding challenge](https://leetcode.com/explore/challenge/card/30-day-leetcoding-challenge/) by [Leetcode](https://leetcode.com/)

### Problem definition: Single number 
Given a non-empty array of integers, every element appears twice except for one. Find that single one.

> Note: Your algorithm should have a linear runtime complexity. Could you implement it without using extra memory?

#### Sample Testcase 

Testcase 1
```
Input: [2,2,1]
Output: 1
```
Testcase 2
```
Input: [4,1,2,1,2]
Output: 4
```
I highly encourage you to attempt this problem on your own before looking at my solution.

## Solution

Although the preferred language for Competitive Coding is C/C++ I have used Python for my accepted solution! 

```python
class Solution:
    def singleNumber(self, nums: List[int]) -> int:
        nums.sort()
        for i in range(0,len(nums),2):
            if(i==len(nums)-1):
                return nums[i]
            elif(nums[i]!=nums[i+1]):
                return nums[i]
```

### Submission Details

**Total test cases passed**: 16/16 \
**Runtime**: 92 ms \
**Memory Usage**: 16.5 MB

>Note: This submission was better than 41.59% of Python3 solutions in terms of runtime. Therefore a better approach to reduce the time complexity can be thought of! :new_moon_with_face:

I would really recommend you to explore this side of the Computer Science and tune in to the journey of competitive programming to write better, cleaner, efficient and optimal code! :grinning:

If you have a better approach to this problem, or for any other queries feel free to reach out to [me]((https://www.linkedin.com/in/vidhi-mody-21629a150))! :innocent:



