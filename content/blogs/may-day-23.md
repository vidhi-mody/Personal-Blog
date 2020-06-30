+++
title = "Interval List Intersections: Day 23 of the May LeetCoding Challenge"
description = "My solution to the question Interval List Intersections by LeetCode"
type = ["blogs","blog"]
tags = [
    "Competitive Coding",
    "Competitive Programming",
    "Algorithms",
    "Data Structures",
]
date = "2020-05-24"
categories = [
    "Competitive Coding",
    "Algorithms",
    "Data Structures",
]
series = ["Competitive Coding"]
[ author ]
  name = "Vidhi Mody"
+++

> *“Bad programmers worry about the code. Good programmers worry about data structures and their relationships.”*\
> ~ Linus Torvalds

Day 23 of the [May LeetCoding Challenge](https://leetcode.com/explore/featured/card/may-leetcoding-challenge/) by [Leetcode](https://leetcode.com/)

### Problem definition: Interval List Intersections

Given two lists of **closed** intervals, each list of intervals is pairwise disjoint and in sorted order.

Return the intersection of these two interval lists.

*(Formally, a closed interval `[a, b]` (with `a <= b`) denotes the set of real numbers `x` with `a <= x <= b`.  The intersection of two closed intervals is a set of real numbers that is either empty, or can be represented as a closed interval.  For example, the intersection of [1, 3] and [2, 4] is [2, 3].)*

#### Sample Testcase 

Testcase 1
![explanation](/img/range.PNG) 
``` 
Input: A = [[0,2],[5,10],[13,23],[24,25]], B = [[1,5],[8,12],[15,24],[25,26]]
Output: [[1,2],[5,5],[8,10],[15,23],[24,24],[25,25]]
Reminder: The inputs and the desired output are lists of Interval objects, and not arrays or lists.
```
> **Note**:
>   1. 0 <= A.length < 1000
>   2. 0 <= B.length < 1000
>   3. 0 <= A[i].start, A[i].end, B[i].start, B[i].end < 10^9

I highly encourage you to attempt this [problem](https://leetcode.com/explore/challenge/card/may-leetcoding-challenge/537/week-4-may-22nd-may-28th/) on your own before looking at my solution.

## Approach

Keep iterating through the list to find the lower and upper bound of intersection and append it to the answer.

## Solution

```python
class Solution(object):
    def intervalIntersection(self, A, B):
        """
        :type A: List[List[int]]
        :type B: List[List[int]]
        :rtype: List[List[int]]
        """
        answer = []
        lenA = len(A)
        lenB = len(B)
        i=0
        j=0
        while(i<lenA and j<lenB):
                lowerBound = max(A[i][0],B[j][0])
                upperBound = min(A[i][1],B[j][1])
                if(lowerBound<=upperBound):
                    answer.append([lowerBound,upperBound])
                if(A[i][1] < B[j][1]):
                    i = i + 1
                else:
                    j = j + 1
        return answer
```

### Submission Details

**Total test cases passed**: 86 / 86 \
**Runtime**: 128 ms \
**Memory Usage**: 13.4 MB 

>Note: This submission was better than 73.78% of Python3 solutions in terms of runtime! Try to come up with a better approach! :new_moon_with_face:

I would really recommend you to explore this side of the Computer Science and tune in to the journey of competitive programming to write better, cleaner, efficient and optimal code! :grinning:

If you have a better approach to this problem, or for any other queries feel free to reach out to [me](https://www.linkedin.com/in/vidhi-mody-21629a150)! :innocent: