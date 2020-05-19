+++
title = "First Bad Version: Day 1 of the May LeetCoding Challenge"
description = ""
type = ["blogs","blog"]
tags = [
    "Competitive Coding",
    "Competitive Programming",
    "Algorithms",
    "Data Structures",
]
date = "2020-05-02"
categories = [
    "Competitive Coding",
    "Algorithms",
    "Data Structures",
]
series = ["Competitive Coding"]
[ author ]
  name = "Vidhi Mody"
+++
> *“There are two ways to write error-free programs; only the third one works.”*


Day 1 of the [May LeetCoding Challenge](https://leetcode.com/explore/featured/card/may-leetcoding-challenge/) by [Leetcode](https://leetcode.com/)

Your logic and approach will improves by practice. If you were smart enough to figure out the most optimal solutions to each problem you would'nt be here to being with. Competitive Programming will train you with algorithmic problems that test the better out of your current logic skills. The more you practice the better you will get! 

### Problem definition: First Bad Version 

You are a product manager and currently leading a team to develop a new product. Unfortunately, the latest version of your product fails the quality check. Since each version is developed based on the previous version, all the versions after a bad version are also bad.

Suppose you have `n` versions `[1, 2, ..., n]` and you want to find out the first bad one, which causes all the following ones to be bad.

You are given an API `bool isBadVersion(version)` which will return whether `version` is bad. Implement a function to find the first bad version. 

> Note: \
    You should minimize the number of calls to the API.

#### Sample Testcase 

Testcase 1
```
Given n = 5, and version = 4 is the first bad version.

call isBadVersion(3) -> false
call isBadVersion(5) -> true
call isBadVersion(4) -> true

Then 4 is the first bad version. 
```

I highly encourage you to attempt this [problem](https://leetcode.com/explore/featured/card/may-leetcoding-challenge/534/week-1-may-1st-may-7th/) on your own before looking at my solution.

## Approach

Since the number of API calls need to be minimized an iterative approach would not give optimal results. However, since the elements are in sorted order I thought of an approach similar to the [Binary Search technique](https://www.geeksforgeeks.org/binary-search/). While an iterative approach gives a time complexity of `O(n)` this spproach yields a time complexity of `O(logn)`

## Solution

```python
def findBadVersion(start,end):
    mid=(start+end)//2
    first=start
    last=end
    if(isBadVersion(first)==True):
        return start
    if(isBadVersion(last)==True and isBadVersion(last)):
        return start
    elif(isBadVersion(mid)==True and isBadVersion(mid-1)==False):
        return(mid)
    elif(isBadVersion(mid)==False):
        return findBadVersion(mid+1,end)
    else:
        return findBadVersion(start,mid-1)
    

class Solution(object):
    def firstBadVersion(self, n):
        """
        :type n: int
        :rtype: int
        """
        answer=findBadVersion(1,n)
        return answer
```

### Submission Details

**Total test cases passed**: 22 / 22 \
**Runtime**: 16 ms \
**Memory Usage**:12.8 MB 

>Note: This submission was better than 69.09% of Python3 solutions in terms of runtime. Think hard and try to come up with a solution that is even better!:new_moon_with_face:

I would really recommend you to explore this side of the Computer Science and tune in to the journey of competitive programming to write better, cleaner, efficient and optimal code! :grinning:

If you have a better approach to this problem, or for any other queries feel free to reach out to [me]((https://www.linkedin.com/in/vidhi-mody-21629a150))! :innocent:



