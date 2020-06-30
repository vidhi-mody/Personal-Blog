+++
title = "Edit Distance: Day 31 of the May LeetCoding Challenge"
description = "My solution to the question Edit Distance by LeetCode"
type = ["blogs","blog"]
tags = [
    "Competitive Coding",
    "Competitive Programming",
    "Algorithms",
    "Data Structures",
]
date = "2020-06-01"
categories = [
    "Competitive Coding",
    "Algorithms",
    "Data Structures",
]
series = ["Competitive Coding"]
[ author ]
  name = "Vidhi Mody"
+++

> *“The big optimizations come from refining the high-level design, not the individual routines.”* \
> ~ Steve McConnell

Day 31 of the [May LeetCoding Challenge](https://leetcode.com/explore/featured/card/may-leetcoding-challenge/) by [Leetcode](https://leetcode.com/)

### Problem definition: Edit Distance

Given two words word1 and word2, find the minimum number of operations required to convert word1 to word2.

You have the following 3 operations permitted on a word:

1. Insert a character
2. Delete a character
3. Replace a character

#### Sample Testcase 

Testcase 1
``` 
Input: word1 = "horse", word2 = "ros"
Output: 3
Explanation: 
horse -> rorse (replace 'h' with 'r')
rorse -> rose (remove 'r')
rose -> ros (remove 'e')
```

Testcase 2
```
Input: word1 = "intention", word2 = "execution"
Output: 5
Explanation: 
intention -> inention (remove 't')
inention -> enention (replace 'i' with 'e')
enention -> exention (replace 'n' with 'x')
exention -> exection (replace 'n' with 'c')
exection -> execution (insert 'u')
```

I highly encourage you to attempt this [problem](https://leetcode.com/explore/challenge/card/may-leetcoding-challenge/538/week-5-may-29th-may-31st/) on your own before looking at my solution.

## Solution

```python
def findDist(word1, word2, len1, len2): 

    minDist = [[0 for x in range(len2 + 1)] for x in range(len1 + 1)] 

    for i in range(len1 + 1): 
        for j in range(len2 + 1): 
            if i == 0: 
                minDist[i][j] = j
                
            elif j == 0: 
                minDist[i][j] = i
                
            elif word1[i-1] == word2[j-1]: 
                minDist[i][j] = minDist[i-1][j-1] 
  
            else: 
                minDist[i][j] = 1 + min(minDist[i][j-1], minDist[i-1][j], minDist[i-1][j-1])
  
    return minDist[len1][len2] 

class Solution(object):
    def minDistance(self, word1, word2):
        """
        :type word1: str
        :type word2: str
        :rtype: int
        """
        answer = findDist(word1, word2, len(word1), len(word2))
        return answer
```

### Submission Details

**Total test cases passed**: 1146 / 1146 \
**Runtime**: 160 ms \
**Memory Usage**: 15.9 MB 

>Note: This submission was better than 40.73% of Python3 solutions in terms of runtime! Try to come up with a better approach! :new_moon_with_face:

Super thrilled to have successfully completed this challenge. For those who missed this one, you can start with the [June LeetCoding Challenge](https://leetcode.com/explore/challenge/card/june-leetcoding-challenge/). Good luck! 

I would really recommend you to explore this side of the Computer Science and tune in to the journey of competitive programming to write better, cleaner, efficient and optimal code! :grinning:

If you have a better approach to this problem, or for any other queries feel free to reach out to [me](https://www.linkedin.com/in/vidhi-mody-21629a150)! :innocent: