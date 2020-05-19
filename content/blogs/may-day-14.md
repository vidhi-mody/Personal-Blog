+++
title = "Implement Trie (Prefix Tree): Day 14 of the May LeetCoding Challenge"
description = ""
type = ["blogs","blog"]
tags = [
    "Competitive Coding",
    "Competitive Programming",
    "Algorithms",
    "Data Structures",
]
date = "2020-05-15"
categories = [
    "Competitive Coding",
    "Algorithms",
    "Data Structures",
]
series = ["Competitive Coding"]
[ author ]
  name = "Vidhi Mody"
+++

> *“Not all roots are buried down in the ground, some are at the top of a tree.”*\
> ~ Jinvirle

Day 14 of the [May LeetCoding Challenge](https://leetcode.com/explore/featured/card/may-leetcoding-challenge/) by [Leetcode](https://leetcode.com/)

### Problem definition: Implement Trie (Prefix Tree)

{{<center src="/img/trie.gif" alt="Trie">}}

Implement a trie with `insert`, `search`, and `startsWith` methods.

> **Note**: 
> - You may assume that all inputs are consist of lowercase letters a-z.
> - All inputs are guaranteed to be non-empty strings.

#### Sample Testcase 

Testcase 1

``` 
Trie trie = new Trie();

trie.insert("apple");
trie.search("apple");   // returns true
trie.search("app");     // returns false
trie.startsWith("app"); // returns true
trie.insert("app");   
trie.search("app");     // returns true
```

I highly encourage you to attempt this [problem](https://leetcode.com/explore/challenge/card/may-leetcoding-challenge/535/week-2-may-8th-may-14th/) on your own before looking at my solution.

## Approach

Before coming to implementation, I suggest you read a bit about [Prefix Trees](https://www.educative.io/edpresso/what-is-a-prefix-treehttps://www.educative.io/edpresso/what-is-a-prefix-tree). It will help you understand the solution better!

## Solution

```python
class Trie:

    def __init__(self):
        """
        Initialize your data structure here.
        """
        self.root={}
        
    def insert(self, word: str) -> None:
        """
        Inserts a word into the trie.
        """
        current=self.root
        for l in word:
            if l not in current:
                current[l]={}
            current=current[l]
        current['$']='$'
        
    def search(self, word: str) -> bool:
        """
        Returns if the word is in the trie.
        """
        current=self.root
        for l in word:
            if(l not in current):
                return False
            current=current[l]
        return '$' in current

    def startsWith(self, prefix: str) -> bool:
        """
        Returns if there is any word in the trie that starts with the given prefix.
        """
        current=self.root
        for l in prefix:
            if(l not in current):
                return False
            current=current[l]
        return True
```

### Submission Details

**Total test cases passed**: 15 / 15 \
**Runtime**: 128 ms \
**Memory Usage**: 27.2 MB 

>Note: This submission was better than 95.31% of Python3 solutions in terms of runtime! Try to come up with a better approach! :new_moon_with_face: 

I would really recommend you to explore this side of the Computer Science and tune in to the journey of competitive programming to write better, cleaner, efficient and optimal code! :grinning:

If you have a better approach to this problem, or for any other queries feel free to reach out to [me](https://www.linkedin.com/in/vidhi-mody-21629a150)! :innocent:
