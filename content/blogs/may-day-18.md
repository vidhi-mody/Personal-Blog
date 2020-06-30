+++
title = "Permutation in String: Day 18 of the May LeetCoding Challenge"
description = "My solution to the question Permutation in String by LeetCode"
type = ["blogs","blog"]
tags = [
    "Competitive Coding",
    "Competitive Programming",
    "Algorithms",
    "Data Structures",
]
date = "2020-05-19"
categories = [
    "Competitive Coding",
    "Algorithms",
    "Data Structures",
]
series = ["Competitive Coding"]
[ author ]
  name = "Vidhi Mody"
+++

> *“Every programmer is an author.”*\
> ~ Sercan Leylek

Day 18 of the [May LeetCoding Challenge](https://leetcode.com/explore/featured/card/may-leetcoding-challenge/) by [Leetcode](https://leetcode.com/)

### Problem definition: Permutation in String

Given two strings **s1** and **s2**, write a function to return true if **s2** contains the permutation of **s1**. In other words, one of the first string's permutations is the **substring** of the second string.

> **Note**: 
>   1. The input strings only contain lower case letters.
>   2. The length of both given strings is in range [1, 10,000].

#### Sample Testcase 

Testcase 1

``` 
Input: s1 = "ab" s2 = "eidbaooo"
Output: True
Explanation: s2 contains one permutation of s1 ("ba").
```

Testcase 2

``` 
Input:s1= "ab" s2 = "eidboaoo"
Output: False
```

I highly encourage you to attempt this [problem](https://leetcode.com/explore/challenge/card/may-leetcoding-challenge/536/week-3-may-15th-may-21st/) on your own before looking at my solution.

## Approach 

This question follows the same approach as the previous problem!
Time Complexity: `O(n)`

## Solution

```python
class Solution:
    def checkInclusion(self, s1: str, s2: str) -> bool:
        s1Hash=0
        s2Hash=0
        
        if len(s2)<len(s1):
            return False
        
        for i in s1:
            s1Hash+=hash(i)
        for i in range(len(s1)):
            s2Hash+=hash(s2[i])

        if s1Hash==s2Hash:
            return True
        
        if len(s2)>len(s1):
            for j in range(len(s1),len(s2)):
                s2Hash+=hash(s2[j])-hash(s2[j-len(s1)])
                if s1Hash==s2Hash:
                    return True
                
        return False 
```

### Submission Details

**Total test cases passed**: 103 / 103 \
**Runtime**: 52 ms \
**Memory Usage**: 13.7 MB 

>Note: This submission was better than 98.00% of Python3 solutions in terms of runtime! Try to come up with a better approach! :new_moon_with_face: 

I would really recommend you to explore this side of the Computer Science and tune in to the journey of competitive programming to write better, cleaner, efficient and optimal code! :grinning:

If you have a better approach to this problem, or for any other queries feel free to reach out to [me](https://www.linkedin.com/in/vidhi-mody-21629a150)! :innocent: