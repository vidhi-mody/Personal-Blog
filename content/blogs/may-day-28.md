+++
title = "Counting Bits: Day 28 of the May LeetCoding Challenge"
description = "My solution to the question Counting Bits by LeetCode"
type = ["blogs","blog"]
tags = [
    "Competitive Coding",
    "Competitive Programming",
    "Algorithms",
    "Data Structures",
]
date = "2020-05-29"
categories = [
    "Competitive Coding",
    "Algorithms",
    "Data Structures",
]
series = ["Competitive Coding"]
[ author ]
  name = "Vidhi Mody"
+++

> *“Premature optimization is the root of all evil.”* \
> ~ Donald Knuth

Day 28 of the [May LeetCoding Challenge](https://leetcode.com/explore/featured/card/may-leetcoding-challenge/) by [Leetcode](https://leetcode.com/)

### Problem definition: Counting Bits

Given a non negative integer number **num**. For every numbers **i** in the range **0 ≤ i ≤ num** calculate the number of 1's in their binary representation and return them as an array.

#### Sample Testcase 

Testcase 1
``` 
Input: 2
Output: [0,1,1]
```

Testcase 2
```
Input: 5
Output: [0,1,1,2,1,2]
```

> **Follow up:**:
> - It is very easy to come up with a solution with run time O(n*sizeof(integer)). But can you do it in linear time O(n) /possibly in a single pass?
> - Space complexity should be O(n).
> - Can you do it like a boss? Do it without using any builtin function like __builtin_popcount in c++ or in any other language.

I highly encourage you to attempt this [problem](https://leetcode.com/explore/challenge/card/may-leetcoding-challenge/537/week-4-may-22nd-may-28th/) on your own before looking at my solution.

## Solution

```python
class Solution(object):
    def countBits(self, num):
        """
        :type num: int
        :rtype: List[int]
        """
        answer = [0] * (num + 1)
        
        for pow in range(0, 32):
            begin = 1<<pow
            end = 1<<(pow + 1)
            if(begin > num):
                break
            for i in range(begin, min(num+1,end)):
                answer[i] = answer[i-begin] + 1
                
        return answer
```

### Submission Details

**Total test cases passed**: 15 / 15 \
**Runtime**: 64 ms \
**Memory Usage**: 15.4 MB 

>Note: This submission was better than 92.05% of Python3 solutions in terms of runtime! Try to come up with a better approach! :new_moon_with_face:

I would really recommend you to explore this side of the Computer Science and tune in to the journey of competitive programming to write better, cleaner, efficient and optimal code! :grinning:

If you have a better approach to this problem, or for any other queries feel free to reach out to [me](https://www.linkedin.com/in/vidhi-mody-21629a150)! :innocent: