+++
title = "Remove K Digits: Day 13 of the May LeetCoding Challenge"
description = ""
type = ["blogs","blog"]
tags = [
    "Competitive Coding",
    "Competitive Programming",
    "Algorithms",
    "Data Structures",
]
date = "2020-05-14"
categories = [
    "Competitive Coding",
    "Algorithms",
    "Data Structures",
]
series = ["Competitive Coding"]
[ author ]
  name = "Vidhi Mody"
+++

> *“I'm a programmer. I like programming. And the best way I've found to have a positive impact on code is to write it.”*\
> ~ Robert C. Martin

Day 13 of the [May LeetCoding Challenge](https://leetcode.com/explore/featured/card/may-leetcoding-challenge/) by [Leetcode](https://leetcode.com/)

### Problem definition: Remove K Digits

{{<center src="/img/removeDigit.gif" alt="Binary Search">}}

Given a non-negative integer num represented as a string, remove k digits from the number so that the new number is the smallest possible.

> **Note**: 
> - The length of num is less than 10002 and will be ≥ k.
> - The given num does not contain any leading zero.

#### Sample Testcase 

Testcase 1

``` 
Input: num = "1432219", k = 3
Output: "1219"
Explanation: Remove the three digits 4, 3, and 2 to form the new number 1219 which is the smallest.
```

Testcase 2

``` 
Input: num = "10200", k = 1
Output: "200"
Explanation: Remove the leading 1 and the number is 200. Note that the output must not contain leading zeroes.
```

Testcase 3

``` 
Input: num = "10", k = 2
Output: "0"
Explanation: Remove all the digits from the number and it is left with nothing which is 0.
```

I highly encourage you to attempt this [problem](https://leetcode.com/explore/challenge/card/may-leetcoding-challenge/535/week-2-may-8th-may-14th/) on your own before looking at my solution.

## Approach

If you observe carefully, if a current number is greater than the number appearing after it, removing that element is the best choice. In case, the digits are in ascending order, the last digit should be removed!

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

**Total test cases passed**: 33 / 33 \
**Runtime**: 1376 ms \
**Memory Usage**: 14 MB 

>Note: A better approach to this solution needs to be devised from my end. Do [hit me up](https://www.linkedin.com/in/vidhi-mody-21629a150) if you have any ideas!

I would really recommend you to explore this side of the Computer Science and tune in to the journey of competitive programming to write better, cleaner, efficient and optimal code! :grinning:

If you have a better approach to this problem, or for any other queries feel free to reach out to [me](https://www.linkedin.com/in/vidhi-mody-21629a150)! :innocent:
