+++
title = "Maximum Sum Circular Subarray: Day 15 of the May LeetCoding Challenge"
description = ""
type = ["blogs","blog"]
tags = [
    "Competitive Coding",
    "Competitive Programming",
    "Algorithms",
    "Data Structures",
]
date = "2020-05-16"
categories = [
    "Competitive Coding",
    "Algorithms",
    "Data Structures",
]
series = ["Competitive Coding"]
[ author ]
  name = "Vidhi Mody"
+++

> *“Programmers are not to be measured by their ingenuity and their logic but by the completeness of their case analysis.”*\
> ~ Alan J. Perlis

Day 15 of the [May LeetCoding Challenge](https://leetcode.com/explore/featured/card/may-leetcoding-challenge/) by [Leetcode](https://leetcode.com/)

### Problem definition: Maximum Sum Circular Subarray

Given a **circular array C** of integers represented by `A`, find the maximum possible sum of a non-empty subarray of **C**.

Here, a circular array means the end of the array connects to the beginning of the array.  (Formally, `C[i] = A[i]` when `0 <= i < A.length`, and `C[i+A.length] = C[i]` when `i >= 0`.)

Also, a subarray may only include each element of the fixed buffer A at most once.  (Formally, for a subarray `C[i], C[i+1], ..., C[j]`, there does not exist `i <= k1, k2 <= j` with `k1 % A.length = k2 % A.length`.)

> **Note**: 
>   1. -30000 <= A[i] <= 30000
>   2. <= A.length <= 30000

#### Sample Testcase 

Testcase 1

``` 
Input: [1,-2,3,-2]
Output: 3
Explanation: Subarray [3] has maximum sum 3
```

Testcase 2

``` 
Input: [5,-3,5]
Output: 10
Explanation: Subarray [5,5] has maximum sum 5 + 5 = 10
```

Testcase 3

``` 
Input: [3,-1,2,-1]
Output: 4
Explanation: Subarray [2,-1,3] has maximum sum 2 + (-1) + 3 = 4
```

Testcase 4

``` 
Input: [3,-2,2,-3]
Output: 3
Explanation: Subarray [3] and [3,-2,2] both have maximum sum 3
```

Testcase 5

``` 
Input: [-2,-3,-1]
Output: -1
Explanation: Subarray [-1] has maximum sum -1
```

I highly encourage you to attempt this [problem](https://leetcode.com/explore/challenge/card/may-leetcoding-challenge/536/week-3-may-15th-may-21st/) on your own before looking at my solution.

## Approach

Before coming to implementation, I highly recommend you to read a bit about [Kadane's Algorithm](https://www.geeksforgeeks.org/largest-sum-contiguous-subarray/). It will help you understand the solution better! 

Now that you are familiar with Kadane's Algorithm, you know how to calculate the maximum sum when the maximum sum subarray is in the middle. For the second case Max sum will be: (Sum of the array)  + Kadane(inverted array).   

## Solution

```python
def kadane(A):  
    current_max = 0
    total_max = 0
    for i in range(0, len(A)): 
        current_max = current_max + A[i] 
        if (current_max < 0): 
            current_max = 0
        if (total_max < current_max): 
            total_max = current_max 
    return total_max 

class Solution:
    def maxSubarraySumCircular(self, A: List[int]) -> int:
        kadane_sum = kadane(A) 
        if(kadane_sum==0 and 0 not in A):
            return max(A)

        total_sum = 0
        for i in range(0,len(A)): 
            total_sum += A[i] 
            A[i] = -A[i] 

        total_sum = total_sum + kadane(A) 

        if total_sum > kadane_sum: 
            return total_sum 
        else: 
            return kadane_sum
```

### Submission Details

**Total test cases passed**: 109 / 109 \
**Runtime**: 472 ms \
**Memory Usage**: 17.9 MB 

>Note: This submission was better than 96.50% of Python3 solutions in terms of runtime! Try to come up with a better approach! :new_moon_with_face: 

I would really recommend you to explore this side of the Computer Science and tune in to the journey of competitive programming to write better, cleaner, efficient and optimal code! :grinning:

If you have a better approach to this problem, or for any other queries feel free to reach out to [me](https://www.linkedin.com/in/vidhi-mody-21629a150)! :innocent:
