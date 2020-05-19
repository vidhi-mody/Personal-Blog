+++
title = "Cousins in Binary Tree: Day 7 of the May LeetCoding Challenge"
description = ""
type = ["blogs","blog"]
tags = [
    "Competitive Coding",
    "Competitive Programming",
    "Algorithms",
    "Data Structures",
]
date = "2020-05-08"
categories = [
    "Competitive Coding",
    "Algorithms",
    "Data Structures",
]
series = ["Competitive Coding"]
[ author ]
  name = "Vidhi Mody"
+++
> *“There is nothing good or bad about knowledge itself; morality lies in the application of knowledge.”*\
>~Jon Erickson


Day 7 of the [May LeetCoding Challenge](https://leetcode.com/explore/featured/card/may-leetcoding-challenge/) by [Leetcode](https://leetcode.com/)

I wanted to share something I read today which could foster in you a deeper desire to continue this journey of learning something new everyday! Learning a new skill helps you learn things faster over time. The white matter in your brain is called myelin, and it helps improve performance when you are working on multiple tasks. The more you practice a new skill that you are learning, the more dense the myelin in your brains becomes, which in turn helps you learn even better. The keyword here is ***Practice***! :trophy:

### Problem definition: Cousins in Binary Tree

In a binary tree, the root node is at depth `0`, and children of each depth `k` node are at depth `k+1`.

Two nodes of a binary tree are *cousins* if they have the same depth, but have **different parents**.

We are given the `root` of a binary tree with unique values, and the values `x` and `y` of two different nodes in the tree.

Return `true` if and only if the nodes corresponding to the values `x` and `y` are cousins.

> Note:
> 1. The number of nodes in the tree will be between `2` and `100`.
> 2. Each node has a unique integer value from `1` to `100`.

#### Sample Testcase 

Testcase 1
![tree1](/img/tree1.PNG) 
```
Input: root = [1,2,3,4], x = 4, y = 3
Output: false
```

Testcase 2
![tree1](/img/tree2.PNG) 
```
Input: root = [1,2,3,null,4,null,5], x = 5, y = 4
Output: true
```

Testcase 3
![tree1](/img/tree3.PNG) 
```
Input: root = [1,2,3,null,4], x = 2, y = 3
Output: false
```

I highly encourage you to attempt this [problem](https://leetcode.com/explore/featured/card/may-leetcoding-challenge/534/week-1-may-1st-may-7th/) on your own before looking at my solution.

## Approach

Iteratively traverse through each node of the tree and store it's depth and parent in a dictionary. \
For two nodes to be cousins check the following conditions:
- The two nodes have equal depth.
- The two nodes have different parents.

{{<center src="/img/traversal.gif" alt="coding">}}

## Solution

```python
class Solution:
    def isCousins(self, root: TreeNode, x: int, y: int) -> bool:
        nodeValue = {}
        def getOrder(node , level , parent):
            if(not node):
                return 0
            nodeValue[node.val] = [level , parent]
            getOrder(node.left , level + 1 , node.val)
            getOrder(node.right , level + 1 , node.val)
        getOrder(root , 0 , -1)
        if((nodeValue[x][0] == nodeValue[y][0]) and (nodeValue[x][1] != nodeValue[y][1])):
            return True
        else:
            return False
```

### Submission Details

**Total test cases passed**: 103 / 103 \
**Runtime**: 36 ms \
**Memory Usage**: 13.9 MB 

>Note: This submission was better than 31.75% of Python3 solutions in terms of runtime. I really should try to come up with a better solution! :sweat_smile: 

This completes Week 1 of the May LeetCoding Challenge. Woohoo! :tada:

I would really recommend you to explore this side of the Computer Science and tune in to the journey of competitive programming to write better, cleaner, efficient and optimal code! :grinning:

If you have a better approach to this problem, or for any other queries feel free to reach out to [me]((https://www.linkedin.com/in/vidhi-mody-21629a150))! :innocent:
