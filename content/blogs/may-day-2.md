+++
title = "Jewels and Stones: Day 2 of the May LeetCoding Challenge"
description = ""
type = ["blogs","blog"]
tags = [
    "Competitive Coding",
    "Competitive Programming",
    "Algorithms",
    "Data Structures",
]
date = "2020-05-03"
categories = [
    "Competitive Coding",
    "Algorithms",
    "Data Structures",
]
series = ["Competitive Coding"]
[ author ]
  name = "Vidhi Mody"
+++
> *“Always code as if the guy who ends up maintaining your code will be a violent psychopath who knows where you live.”*


Day 2 of the [May LeetCoding Challenge](https://leetcode.com/explore/featured/card/may-leetcoding-challenge/) by [Leetcode](https://leetcode.com/)

With practice, you will develop an improved logic and you will learn to write code which is both fast and optimal. You will be able to think faster, solve problems faster and code faster! Competitive programming might just be the best way of learning something new! 

### Problem definition: Jewels and Stones

{{<center src="/img/jewels.gif" alt="Jewels">}}

You're given strings `J` representing the types of stones that are jewels, and `S` representing the stones you have.  Each character in `S` is a type of stone you have. You want to know how many of the stones you have are also jewels.

The letters in `J` are guaranteed distinct, and all characters in `J` and `S` are letters. Letters are case sensitive, so `"a"` is considered a different type of stone from `"A"`.

> Note: 
>- `S` and `J` will consist of letters and have length at most 50.
>- The characters in `J` are distinct.

#### Sample Testcase 

Testcase 1
```
Input: J = "aA", S = "aAAbbbb"
Output: 3
```

Testcase 2
```
Input: J = "z", S = "ZZ"
Output: 0
```

I highly encourage you to attempt this [problem](https://leetcode.com/explore/featured/card/may-leetcoding-challenge/534/week-1-may-1st-may-7th/) on your own before looking at my solution.

## Approach

The hint `For each stone, check if it is a jewel.` gives a clear idea of the approach to be followed. Iteratively scan across each stone and determine if the stone is a jewel. If it is, increment the counter.

## Solution

```python
class Solution(object):
    def numJewelsInStones(self, J, S):
        """
        :type J: str
        :type S: str
        :rtype: int
        """
        count=0
        for i in range(len(S)):
            if(S[i] in J):
                count=count+1
        return count
```

### Submission Details

**Total test cases passed**: 254 / 254 \
**Runtime**: 16 ms \
**Memory Usage**:12.9 MB 

>Note: This submission was better than 84.04% of Python3 solutions in terms of runtime. Think hard and try to come up with a solution that is even better! :new_moon_with_face:

I would really recommend you to explore this side of the Computer Science and tune in to the journey of competitive programming to write better, cleaner, efficient and optimal code! :grinning:

If you have a better approach to this problem, or for any other queries feel free to reach out to [me]((https://www.linkedin.com/in/vidhi-mody-21629a150))! :innocent:



