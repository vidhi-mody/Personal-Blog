+++
title = "Contiguous Array: Day 26 of the May LeetCoding Challenge"
description = "My solution to the question Contiguous Array by LeetCode"
type = ["blogs","blog"]
tags = [
    "Competitive Coding",
    "Competitive Programming",
    "Algorithms",
    "Data Structures",
]
date = "2020-05-27"
categories = [
    "Competitive Coding",
    "Algorithms",
    "Data Structures",
]
series = ["Competitive Coding"]
[ author ]
  name = "Vidhi Mody"
+++

> *“It is better to have 100 functions operate on one data structure than to have 10 functions operate on 10 data structures.”* \
> ~ Alan Perlis

Day 26 of the [May LeetCoding Challenge](https://leetcode.com/explore/featured/card/may-leetcoding-challenge/) by [Leetcode](https://leetcode.com/)

### Problem definition: Contiguous Array

Given a binary array, find the maximum length of a contiguous subarray with equal number of 0 and 1.

#### Sample Testcase 

Testcase 1

``` 
Input: [0,1]
Output: 2
Explanation: [0, 1] is the longest contiguous subarray with equal number of 0 and 1.
```

Testcase 2
```
Input: [0,1,0]
Output: 2
Explanation: [0, 1] (or [1, 0]) is a longest contiguous subarray with equal number of 0 and 1.
```

> **Note**: The length of the given binary array will not exceed 50,000.

I highly encourage you to attempt this [problem](https://leetcode.com/explore/challenge/card/may-leetcoding-challenge/537/week-4-may-22nd-may-28th/) on your own before looking at my solution.

## Solution

```python
class Solution(object):
    def findMaxLength(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        if(len(nums)<=1):
            return 0
        count=0
        maxLength=0
        counter={0:-1}
        for index, value in enumerate(nums): 
            
            
            if(value==1):
                count = count + 1
            
            else:
                count = count - 1
           
            if count in counter:
                maxLength=max(maxLength,index-counter[count])
                
            else:
                counter[count]=index
            print(index, counter, maxLength)
        return maxLength
```

### Submission Details

**Total test cases passed**: 555 / 555 \
**Runtime**: 792 ms \
**Memory Usage**: 16.2 MB 

>Note: This submission was better than 74.92% of Python3 solutions in terms of runtime! Try to come up with a better approach! :new_moon_with_face:

I would really recommend you to explore this side of the Computer Science and tune in to the journey of competitive programming to write better, cleaner, efficient and optimal code! :grinning:

If you have a better approach to this problem, or for any other queries feel free to reach out to [me](https://www.linkedin.com/in/vidhi-mody-21629a150)! :innocent: