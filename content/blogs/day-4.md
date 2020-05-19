+++
title = "Move Zeroes: Day 4 of the 30 days coding challenge"
description = ""
type = ["blogs","blog"]
tags = [
    "Competitive Coding",
    "Competitive Programming",
    "Algorithms",
    "Data Structures",
]
date = "2020-04-22"
categories = [
    "Competitive Coding",
    "Algorithms",
    "Data Structures",
]
series = ["Competitive Coding"]
[ author ]
  name = "Vidhi Mody"
+++
> *“Don’t worry if it doesn’t work right. If everything did, you’d be out of a job.”* \
> ~ (Mosher’s Law of Software Engineering)


Day 4 of the [30 days coding challenge](https://leetcode.com/explore/challenge/card/30-day-leetcoding-challenge/) by [Leetcode](https://leetcode.com/)

Setting daily targets and achieving them is the best way to go forward! (Just a random suggestion!:information_desk_person:)

### Problem definition: Move Zeroes 

Given an array `nums`, write a function to move all 0's to the end of it while maintaining the relative order of the non-zero elements.

> Note: \
    You must do this in-place without making a copy of the array. \
    Minimize the total number of operations.

#### Sample Testcase 

Testcase 1
```
Input: [0,1,0,3,12]
Output: [1,3,12,0,0]
```

I highly encourage you to attempt this problem on your own before looking at my solution.

## Solution

```python
class Solution:
    def moveZeroes(self, nums: List[int]) -> None:
        """
        Do not return anything, modify nums in-place instead.
        """
        count=0
        for i in range(0,len(nums)):
            if(nums[i]!=0):
                nums[count]= nums[i]
                count=count+1
        for i in range(count,len(nums)):
            nums[i]=0
```

### Submission Details

**Total test cases passed**: 21/21 \
**Runtime**: 32 ms \
**Memory Usage**:13.6 MB 

>Note: This submission was better than 93.09% of Python3 solutions in terms of runtime. Think hard and try to come up with a solution that is even better!:new_moon_with_face:

I would really recommend you to explore this side of the Computer Science and tune in to the journey of competitive programming to write better, cleaner, efficient and optimal code! :grinning:

If you have a better approach to this problem, or for any other queries feel free to reach out to [me]((https://www.linkedin.com/in/vidhi-mody-21629a150))! :innocent:



