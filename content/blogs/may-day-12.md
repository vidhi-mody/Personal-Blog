+++
title = "Single Element in a Sorted Array: Day 12 of the May LeetCoding Challenge"
description = ""
type = ["blogs","blog"]
tags = [
    "Competitive Coding",
    "Competitive Programming",
    "Algorithms",
    "Data Structures",
]
date = "2020-05-13"
categories = [
    "Competitive Coding",
    "Algorithms",
    "Data Structures",
]
series = ["Competitive Coding"]
[ author ]
  name = "Vidhi Mody"
+++

> *“Learning to write programs stretches your mind, and helps you think better, creates a way of thinking about things that I think is helpful in all domains.”*\
>~Bill Gates

Day 12 of the [May LeetCoding Challenge](https://leetcode.com/explore/featured/card/may-leetcoding-challenge/) by [Leetcode](https://leetcode.com/)

### Problem definition: Single Element in a Sorted Array

You are given a sorted array consisting of only integers where every element appears exactly twice, except for one element which appears exactly once. Find this single element that appears only once.

> **Note**: Your solution should run in O(log n) time and O(1) space.

#### Sample Testcase 

Testcase 1

``` 
Input: [1,1,2,3,3,4,4,8,8]
Output: 2
```

Testcase 2

``` 
Input: [3,3,7,7,10,11,11]
Output: 10
```

I highly encourage you to attempt this [problem](https://leetcode.com/explore/challenge/card/may-leetcoding-challenge/535/week-2-may-8th-may-14th/) on your own before looking at my solution.

## Approach

Since the array is sorted, a modified approach to Binary Search can be used to find the single element.

{{<center src="/img/binary_search.gif" alt="Binary Search">}}

## Solution

```python
def findDuplicate(start,end,nums):  
    
    if(start==end):
        return(nums[end])
    
    mid = start + (end-start)//2

    if(mid%2==0):
        if(nums[mid]==nums[mid+1]):
            return findDuplicate(mid+2,end,nums)
        else:
            return findDuplicate(start,mid,nums)
    else:
        if(nums[mid] == nums[mid-1]): 
            return findDuplicate(mid+1, end, nums) 
        else: 
            return findDuplicate(start, mid-1, nums) 
                
class Solution:
    def singleNonDuplicate(self, nums: List[int]) -> int:
        answer = findDuplicate(0,len(nums)-1,nums)
        return answer
```

### Submission Details

**Total test cases passed**: 12 / 12 \
**Runtime**: 72 ms \
**Memory Usage**: 16.1 MB 

>Note: This submission was better than 69.67% of Python3 solutions in terms of runtime! Try to come up with a better approach! :new_moon_with_face: 

I would really recommend you to explore this side of the Computer Science and tune in to the journey of competitive programming to write better, cleaner, efficient and optimal code! :grinning:

If you have a better approach to this problem, or for any other queries feel free to reach out to [me]((https://www.linkedin.com/in/vidhi-mody-21629a150))! :innocent:
