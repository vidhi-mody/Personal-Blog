+++
title = "Ransom Note: Day 3 of the May LeetCoding Challenge"
description = ""
type = ["blogs","blog"]
tags = [
    "Competitive Coding",
    "Competitive Programming",
    "Algorithms",
    "Data Structures",
]
date = "2020-05-04"
categories = [
    "Competitive Coding",
    "Algorithms",
    "Data Structures",
]
series = ["Competitive Coding"]
[ author ]
  name = "Vidhi Mody"
+++
> *“Any fool can write code that a computer can understand. Good programmers write code that humans can understand."*\
>~Martin Fowler


Day 3 of the [May LeetCoding Challenge](https://leetcode.com/explore/featured/card/may-leetcoding-challenge/) by [Leetcode](https://leetcode.com/)

You may always feel that whatever you do isn’t enough, there will always be someone who is better than you. That’s not bad. Don't let that keep you down. Focus on making yourself better. The way I see things there's only one way for that: *Practice, practice and practice!*

### Problem definition: Ransom Note

Given an arbitrary ransom note string and another string containing letters from all the magazines, write a function that will return `true` if the ransom note can be constructed from the magazines ; otherwise, it will return `false`.

Each letter in the magazine string can only be used once in your ransom note.

> Note: \
You may assume that both strings contain only lowercase letters.

#### Sample Testcase 

Testcase 1
```
canConstruct("a", "b") -> false
```

Testcase 2
```
canConstruct("aa", "ab") -> false
```

Testcase 3
```
canConstruct("aa", "aab") -> true
```

I highly encourage you to attempt this [problem](https://leetcode.com/explore/featured/card/may-leetcoding-challenge/534/week-1-may-1st-may-7th/) on your own before looking at my solution.

## Approach

Since the length of the ransom note, has to be smaller than the magazine for the result to be true it makes sense to iteratively search the ransomNote and check if it's elements are present in the magazine. In addition, since every character can be used only once it would be wise to remove the characters already used once!

## Solution

```python
class Solution(object):
    def canConstruct(self, ransomNote, magazine):
        """
        :type ransomNote: str
        :type magazine: str
        :rtype: bool
        """
        count=0
        if(len(ransomNote)>len(magazine)):
            return False
        else: 
            for i in range(len(ransomNote)):
                if(ransomNote[i] in magazine):
                    magazine=magazine.replace(ransomNote[i],'',1)
                    count=count+1
                else:
                    return False
            if(count==len(ransomNote)):
                return True
            else:
                return False
```

### Submission Details

**Total test cases passed**: 126 / 126 \
**Runtime**: 124 ms \
**Memory Usage**: 13.2 MB 

>Note: This submission was better than 12.37% of Python3 solutions in terms of runtime. Think hard and try to come up with a solution that is more optimal! :new_moon_with_face:

I would really recommend you to explore this side of the Computer Science and tune in to the journey of competitive programming to write better, cleaner, efficient and optimal code! :grinning:

If you have a better approach to this problem, or for any other queries feel free to reach out to [me]((https://www.linkedin.com/in/vidhi-mody-21629a150))! :innocent:



