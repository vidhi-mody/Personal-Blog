+++
title = "Possible Bipartition: Day 27 of the May LeetCoding Challenge"
description = "My solution to the question Possible Bipartition by LeetCode"
type = ["blogs","blog"]
tags = [
    "Competitive Coding",
    "Competitive Programming",
    "Algorithms",
    "Data Structures",
]
date = "2020-05-28"
categories = [
    "Competitive Coding",
    "Algorithms",
    "Data Structures",
]
series = ["Competitive Coding"]
[ author ]
  name = "Vidhi Mody"
+++

> *“Without requirements or design, programming is the art of adding bugs to an empty text file.”* \
> ~ Louis Srygley

Day 27 of the [May LeetCoding Challenge](https://leetcode.com/explore/featured/card/may-leetcoding-challenge/) by [Leetcode](https://leetcode.com/)

### Problem definition: Possible Bipartition

Given a set of `N` people (numbered `1, 2, ..., N`), we would like to split everyone into two groups of **any** size.

Each person may dislike some other people, and they should not go into the same group. 

Formally, if `dislikes[i] = [a, b]`, it means it is not allowed to put the people numbered `a` and `b` into the same group.

Return `true` if and only if it is possible to split everyone into two groups in this way.

#### Sample Testcase 

Testcase 1
``` 
Input: N = 4, dislikes = [[1,2],[1,3],[2,4]]
Output: true
Explanation: group1 [1,4], group2 [2,3]
```

Testcase 2
```
Input: N = 3, dislikes = [[1,2],[1,3],[2,3]]
Output: false
```

Testcase 3
```
Input: N = 5, dislikes = [[1,2],[2,3],[3,4],[4,5],[1,5]]
Output: false
```

> **Note**:
>   1. 1 <= N <= 2000
>   2. 0 <= dislikes.length <= 10000
>   3. 1 <= dislikes[i][j] <= N
>   4. dislikes[i][0] < dislikes[i][1]
>   5. There does not exist i != j for which dislikes[i] == dislikes[j].

I highly encourage you to attempt this [problem](https://leetcode.com/explore/challenge/card/may-leetcoding-challenge/537/week-4-may-22nd-may-28th/) on your own before looking at my solution.

## Solution

```python
class Solution(object):
    def possibleBipartition(self, N, dislikes):
        """
        :type N: int
        :type dislikes: List[List[int]]
        :rtype: bool
        """
        if(N<=2):
            return True
        
        if(len(dislikes)<=1):
            return True
        
        while(dislikes):
            remaining = []
            group1 = set()
            group2 = set()
            group1.add(dislikes[0][0])
            group2.add(dislikes[0][1])
            for i in range(1, len(dislikes)):
                a, b = dislikes[i][0], dislikes[i][1]
                if a in group1 and b in group1:
                    return False
                elif a in group2 and b in group2:
                    return False
                elif a in group1 and b in group2:
                    continue
                elif a in group2 and b in group1:
                    continue
                elif a in group1:
                    group2.add(b)
                elif b in group1:
                    group2.add(a)
                elif a in group2:
                    group1.add(b)
                elif b in group2:
                    group1.add(a)
                else:
                    remaining.append(dislikes[i])
            dislikes = remaining
            
        return True
```

### Submission Details

**Total test cases passed**: 66 / 66 \
**Runtime**: 1060 ms \
**Memory Usage**: 18.1 MB 

>Note: This submission was better than 13.23% of Python3 solutions in terms of runtime! Try to come up with a better approach! :new_moon_with_face:

I would really recommend you to explore this side of the Computer Science and tune in to the journey of competitive programming to write better, cleaner, efficient and optimal code! :grinning:

If you have a better approach to this problem, or for any other queries feel free to reach out to [me](https://www.linkedin.com/in/vidhi-mody-21629a150)! :innocent: