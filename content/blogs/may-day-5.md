+++
title = "First Unique Character in a String: Day 5 of the May LeetCoding Challenge"
description = ""
type = ["blogs","blog"]
tags = [
    "Competitive Coding",
    "Competitive Programming",
    "Algorithms",
    "Data Structures",
]
date = "2020-05-06"
categories = [
    "Competitive Coding",
    "Algorithms",
    "Data Structures",
]
series = ["Competitive Coding"]
[ author ]
  name = "Vidhi Mody"
+++
> *“Learning to code is useful no matter what your career ambitions are.”*\
>~Arianna Huffington


Day 5 of the [May LeetCoding Challenge](https://leetcode.com/explore/featured/card/may-leetcoding-challenge/) by [Leetcode](https://leetcode.com/)

Creativity, problem solving, learning and building things is not easy. Competitive coding is like a brain sport. And just like any other sport you can excel in this one only by *practice*!

### Problem definition: First Unique Character in a String

Given a string, find the first non-repeating character in it and return it's index. If it doesn't exist, return -1.

> Note: You may assume the string contain only lowercase letters.

#### Sample Testcase 

Testcase 1
```
s = "leetcode"
return 0.
```

Testcase 2
```
s = "loveleetcode",
return 2.
```

I highly encourage you to attempt this [problem](https://leetcode.com/explore/featured/card/may-leetcoding-challenge/534/week-1-may-1st-may-7th/) on your own before looking at my solution.

## Approach

Iteratively traverse through the string, and create a dictionary to store the occurence of each character and a list to store the unique characters of the string. \
Next, traverse through the list of unique characters and check it's corresponding count in the dictionary. If the count is equal to 1 return the index of that character in the given string.

## Solution

```python
def first_non_repeating_character(str1):
  unique_char = []
  counter = {}
  for c in str1:
    if c in counter:
      counter[c] += 1
    else:
      counter[c] = 1 
      unique_char.append(c)
  for c in unique_char:
    if counter[c] == 1:
      return str1.index(c)
  return -1

class Solution(object):
    def firstUniqChar(self, s):
        """
        :type s: str
        :rtype: int
        """
        index = first_non_repeating_character(s)
        return index  
```

### Submission Details

**Total test cases passed**: 104 / 104 \
**Runtime**: 88 ms \
**Memory Usage**: 13 MB 

>Note: This submission was better than 91.31% of Python3 solutions in terms of runtime. If you come up with something even better, [do hit me up](https://www.linkedin.com/in/vidhi-mody-21629a150)! :new_moon_with_face: 

I would really recommend you to explore this side of the Computer Science and tune in to the journey of competitive programming to write better, cleaner, efficient and optimal code! :grinning:

If you have a better approach to this problem, or for any other queries feel free to reach out to [me]((https://www.linkedin.com/in/vidhi-mody-21629a150))! :innocent:
