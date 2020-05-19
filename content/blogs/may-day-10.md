+++
title = "Find the Town Judge: Day 10 of the May LeetCoding Challenge"
description = ""
type = ["blogs","blog"]
tags = [
    "Competitive Coding",
    "Competitive Programming",
    "Algorithms",
    "Data Structures",
]
date = "2020-05-11"
categories = [
    "Competitive Coding",
    "Algorithms",
    "Data Structures",
]
series = ["Competitive Coding"]
[ author ]
  name = "Vidhi Mody"
+++

> *“Everyone knows that debugging is twice as hard as writing a program in the first place. So if you're as clever as you can be when you write it, how will you ever debug it?”* \
> ~Brian Kernighan

Day 10 of the [May LeetCoding Challenge](https://leetcode.com/explore/featured/card/may-leetcoding-challenge/) by [Leetcode](https://leetcode.com/)

Gaining knowledge is only half the battle won. Many believe that intellectual understanding is enough, to master what they are doing. But the truth is skill development through practice and feedback is always imperative. Making a commitment to practice is essential to maximize the impact of training. After all, practice is the only way to become proficient in a new skill or behavior!


### Problem definition: Find the Town Judge

{{<center src="/img/mayor.gif" alt="Town Judge">}}

In a town, there are `N` people labelled from `1` to `N`.  There is a rumor that one of these people is secretly the town judge.

If the town judge exists, then:
1. The town judge trusts nobody.
2. Everybody (except for the town judge) trusts the town judge.
3. There is exactly one person that satisfies properties 1 and 2.

You are given `trust`, an array of pairs `trust[i] = [a, b]` representing that the person labelled `a` trusts the person labelled `b`.

If the town judge exists and can be identified, return the label of the town judge.  Otherwise, return `-1`.

> **Note**: \
> 1. 1 <= N <= 1000
> 2. trust.length <= 10000
> 3. trust[i] are all different
> 4. trust[i][0] != trust[i][1]
> 5. 1 <= trust[i][0], trust[i][1] <= N

#### Sample Testcase 

Testcase 1

```
Input: N = 2, trust = [[1,2]]
Output: 2
```

Testcase 2

```
Input: N = 3, trust = [[1,3],[2,3]]
Output: 3
```
Testcase 3

```
Input: N = 3, trust = [[1,3],[2,3],[3,1]]
Output: -1
```
Testcase 4

```
Input: N = 3, trust = [[1,2],[2,3]]
Output: -1
```
Testcase 5

```
Input: N = 4, trust = [[1,3],[1,4],[2,3],[2,4],[4,3]]
Output: 3
```

I highly encourage you to attempt this [problem](https://leetcode.com/explore/challenge/card/may-leetcoding-challenge/535/week-2-may-8th-may-14th/) on your own before looking at my solution.

## Approach

For the given list: `trust[i] = [a, b]` we can conclude the following:
- Since the judge does not trust anybody the judge will not have an entry as `a`
- For b to be the judge, b must appear `n-1` in the list

## Solution

```python
class Solution:
    def findJudge(self, N: int, trust: List[List[int]]) -> int:
        if(N==1):
            return 1
        else:
            trustedPeople={}
            townPeople = []
            for i in range(len(trust)):
                townPeople.append(trust[i][0])
                if(trust[i][1] in trustedPeople):
                    trustedPeople[trust[i][1]] += 1
                else:
                    trustedPeople[trust[i][1]] = 1
            for key, value in trustedPeople.items(): 
                if((value == N-1) and (key not in townPeople)):
                    return key
            return -1
```

### Submission Details

**Total test cases passed**: 89 / 89 \
**Runtime**: 796 ms \
**Memory Usage**: 18.3 MB 

>Note: This submission was better than 56.63% of Python3 solutions in terms of runtime! Try to come up with a better approach! :new_moon_with_face: 

I would really recommend you to explore this side of the Computer Science and tune in to the journey of competitive programming to write better, cleaner, efficient and optimal code! :grinning:

If you have a better approach to this problem, or for any other queries feel free to reach out to [me]((https://www.linkedin.com/in/vidhi-mody-21629a150))! :innocent:
