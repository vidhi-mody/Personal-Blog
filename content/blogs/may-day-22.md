+++
title = "Sort Characters By Frequency: Day 22 of the May LeetCoding Challenge"
description = "My solution to the question Sort Characters By Frequency by LeetCode"
type = ["blogs","blog"]
tags = [
    "Competitive Coding",
    "Competitive Programming",
    "Algorithms",
    "Data Structures",
]
date = "2020-05-23"
categories = [
    "Competitive Coding",
    "Algorithms",
    "Data Structures",
]
series = ["Competitive Coding"]
[ author ]
  name = "Vidhi Mody"
+++

> *“There are only two kinds of languages: the ones people complain about and the ones nobody uses.”*\
> ~ Bjarne Stroustrup

Day 22 of the [May LeetCoding Challenge](https://leetcode.com/explore/featured/card/may-leetcoding-challenge/) by [Leetcode](https://leetcode.com/)

### Problem definition: Sort Characters By Frequency

Given a string, sort it in decreasing order based on the frequency of characters.

#### Sample Testcase 

Testcase 1

``` 
Input:
"tree"

Output:
"eert"

Explanation:
'e' appears twice while 'r' and 't' both appear once.
So 'e' must appear before both 'r' and 't'. Therefore "eetr" is also a valid answer.
```

Testcase 2

``` 
Input:
"cccaaa"

Output:
"cccaaa"

Explanation:
Both 'c' and 'a' appear three times, so "aaaccc" is also a valid answer.
Note that "cacaca" is incorrect, as the same characters must be together.
```

Testcase 3

```
Input:
"Aabb"

Output:
"bbAa"

Explanation:
"bbaA" is also a valid answer, but "Aabb" is incorrect.
Note that 'A' and 'a' are treated as two different characters.
```

I highly encourage you to attempt this [problem](https://leetcode.com/explore/challenge/card/may-leetcoding-challenge/537/week-4-may-22nd-may-28th/) on your own before looking at my solution.

## Approach

Store the frequency of each letter in a dictionary. Select the letter with maximum frequency and add it to the answer string.

## Solution

```python
class Solution(object):
    def frequencySort(self, s):
        """
        :type s: str
        :rtype: str
        """
        my_dict={}
        answer=""
        for x in s:
            if(x not in my_dict):
                my_dict[x]=1
            else:
                my_dict[x]+=1
        print(my_dict)
        for i in range(len(my_dict)):
            Keymax = max(my_dict, key=my_dict.get) 
            answer=answer+ Keymax*(my_dict[Keymax])
            del my_dict[Keymax]
        return answer
```

### Submission Details

**Total test cases passed**: 35 / 35 \
**Runtime**: 72 ms \
**Memory Usage**: 15.1 MB 

>Note: This submission was better than 30.30% of Python3 solutions in terms of runtime! Try to come up with a better approach! :new_moon_with_face:

I would really recommend you to explore this side of the Computer Science and tune in to the journey of competitive programming to write better, cleaner, efficient and optimal code! :grinning:

If you have a better approach to this problem, or for any other queries feel free to reach out to [me](https://www.linkedin.com/in/vidhi-mody-21629a150)! :innocent: