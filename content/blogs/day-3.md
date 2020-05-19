+++
title = "Maximum Subarray: Day 3 of the 30 days coding challenge"
description = ""
type = ["blogs","blog"]
tags = [
    "Competitive Coding",
    "Competitive Programming",
    "Algorithms",
    "Data Structures",
]
date = "2020-04-20"
categories = [
    "Competitive Coding",
    "Algorithms",
    "Data Structures",
]
series = ["Competitive Coding"]
[ author ]
  name = "Vidhi Mody"
+++
> *“The most important property of a program is whether it accomplishes the intention of its user.”* \
> ~C.A.R. Hoare

Day 3 of the [30 days coding challenge](https://leetcode.com/explore/challenge/card/30-day-leetcoding-challenge/) by [Leetcode](https://leetcode.com/)

It's been a while since I attempted a new problem! I really need to start making time for daily practice and I suggest you do the same too!:innocent:

### Problem definition: Maximum Subarray
Given an integer array `nums`, find the contiguous subarray (containing at least one number) which has the largest sum and return its sum.

> Follow up: If you have figured out the O(n) solution, try coding another solution using the divide and conquer approach, which is more subtle.

#### Sample Testcase 

Testcase 1
```
Input: [-2,1,-3,4,-1,2,1,-5,4],
Output: 6
Explanation: [4,-1,2,1] has the largest sum = 6.
```

I highly encourage you to attempt this problem on your own before looking at my solution.

## Solution

Although the preferred language for Competitive Coding is C/C++ I have used Python for my accepted solution! 

```python
class Solution(object):
    def maxSubArray(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        n = len(nums)
        max1 =nums[0] 
        curr_max = nums[0] 

        for i in range(1,n): 
            curr_max = max(nums[i], curr_max + nums[i]) 
            max1 = max(max1,curr_max) 

        return max1
```

### Submission Details

**Total test cases passed**: 202 / 202 \
**Runtime**: 44 ms \
**Memory Usage**: 13.1 MB

>Note: This submission was better than 95.89% of Python3 solutions in terms of runtime. However, I still encourage you to come up with a more optimal approach!:new_moon_with_face:

I would really recommend you to explore this side of the Computer Science and tune in to the journey of competitive programming to write better, cleaner, efficient and optimal code! :grinning:

If you have a better approach to this problem, or for any other queries feel free to reach out to [me]((https://www.linkedin.com/in/vidhi-mody-21629a150))! :innocent:



