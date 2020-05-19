+++
title = "Find All Anagrams in a String: Day 17 of the May LeetCoding Challenge"
description = "My solution to the question Find All Anagrams in a String by LeetCode"
type = ["blogs","blog"]
tags = [
    "Competitive Coding",
    "Competitive Programming",
    "Algorithms",
    "Data Structures",
]
date = "2020-05-18"
categories = [
    "Competitive Coding",
    "Algorithms",
    "Data Structures",
]
series = ["Competitive Coding"]
[ author ]
  name = "Vidhi Mody"
+++

> *“Think like a fundamentalist, code like a hacker.”*\
> ~ Erik Meijer

Day 17 of the [May LeetCoding Challenge](https://leetcode.com/explore/featured/card/may-leetcoding-challenge/) by [Leetcode](https://leetcode.com/)

### Problem definition: Find All Anagrams in a String

Given a string **s** and a **non-empty** string **p**, find all the start indices of **p**'s anagrams in **s**.

Strings consists of lowercase English letters only and the length of both strings **s** and **p** will not be larger than 20,100.

The order of output does not matter.

#### Sample Testcase 

Testcase 1

``` 
Input:
s: "cbaebabacd" p: "abc"

Output:
[0, 6]

Explanation:
The substring with start index = 0 is "cba", which is an anagram of "abc".
The substring with start index = 6 is "bac", which is an anagram of "abc".
```

Testcase 2

``` 
Input:
s: "abab" p: "ab"

Output:
[0, 1, 2]

Explanation:
The substring with start index = 0 is "ab", which is an anagram of "ab".
The substring with start index = 1 is "ba", which is an anagram of "ab".
The substring with start index = 2 is "ab", which is an anagram of "ab".
```

I highly encourage you to attempt this [problem](https://leetcode.com/explore/challenge/card/may-leetcoding-challenge/536/week-3-may-15th-may-21st/) on your own before looking at my solution.

## Approach 1

One approach to this problem would be the Sliding Window Technique. In this technique we first create a window of length equal to `p-1`. Then with the window currently at 0 we store the occurences of each letter using a counter and compare it with the occurence of each letter in the string `p`. 

## Solution 1

```python
from collections import Counter
class Solution:
    def findAnagrams(self, s: str, p: str) -> List[int]:
        window = len(p)-1
        countS = collections.Counter(s[:window])
        countP = collections.Counter(p)
        answer = []
        for i,c in enumerate(s[window:]):
            countS[c]+=1
            if countS == countP: 
                answer.append(i)
            countS -= collections.Counter(s[i])
        return answer
```

## Approach 2

The following approach is more optimal than the previous approach. The total hash value of string `p` can be computed. Both strings must have same character frequencies, if one is anagram of another. Therefore their hash value will be the same. For all substrings having same hash value as that of p, their index can be appended to the answer. \
Time Complexity: `O(n)`

## Solution 2

```python
class Solution:
    def findAnagrams(self, s: str, p: str) -> List[int]:
        s1Hash=0
        s2Hash=0
        answer=[]
        
        if len(s)<len(p):
            return answer
        
        for i in range(len(p)):
            s1Hash+=hash(s[i])
        for i in range(len(p)):
            s2Hash+=hash(p[i])
            
        if s1Hash==s2Hash:
            answer.append(0)
        
        if len(s)>len(p):
            i=1
            for j in range(len(p),len(s)): 
                s1Hash+=hash(s[j])-hash(s[j-len(p)])
                if s1Hash==s2Hash:
                    answer.append(i)
                i=i+1
                
        return answer
```

### Submission Details

**Total test cases passed**: 36 / 36 \
**Runtime**: 88 ms \
**Memory Usage**: 15 MB 

>Note: This submission was better than 96.12% of Python3 solutions in terms of runtime! Try to come up with a better approach! :new_moon_with_face: 

I would really recommend you to explore this side of the Computer Science and tune in to the journey of competitive programming to write better, cleaner, efficient and optimal code! :grinning:

If you have a better approach to this problem, or for any other queries feel free to reach out to [me](https://www.linkedin.com/in/vidhi-mody-21629a150)! :innocent:
