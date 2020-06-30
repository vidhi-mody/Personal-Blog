+++
title = "Construct Binary Search Tree from Preorder Traversal: Day 24 of the May LeetCoding Challenge"
description = "My solution to the question Construct Binary Search Tree from Preorder Traversal by LeetCode"
type = ["blogs","blog"]
tags = [
    "Competitive Coding",
    "Competitive Programming",
    "Algorithms",
    "Data Structures",
]
date = "2020-05-25"
categories = [
    "Competitive Coding",
    "Algorithms",
    "Data Structures",
]
series = ["Competitive Coding"]
[ author ]
  name = "Vidhi Mody"
+++

> *“One of the best programming skills you can have is knowing when to walk away for awhile.”*\
> ~ Oscar Godson

Day 24 of the [May LeetCoding Challenge](https://leetcode.com/explore/featured/card/may-leetcoding-challenge/) by [Leetcode](https://leetcode.com/)

### Problem definition: Construct Binary Search Tree from Preorder Traversal

Return the root node of a binary **search** tree that matches the given `preorder` traversal.

*(Recall that a binary search tree is a binary tree where for every node, any descendant of `node.left` has a value `< node.val`, and any descendant of `node.right` has a value `>` `node.val`.  Also recall that a preorder traversal displays the value of the `node` first, then traverses `node.left`, then traverses `node.right`.)*

It's guaranteed that for the given test cases there is always possible to find a binary search tree with the given requirements.

#### Sample Testcase 

Testcase 1

``` 
Input: [8,5,1,7,10,12]
Output: [8,5,10,1,7,null,12]
```
![Binary Search Tree](/img/BST.PNG) 

> **Constraints**:
>   - `1 <= preorder.length <= 100`
>   - `1 <= preorder[i] <= 10^8`
>   - The values of `preorder` are distinct.

I highly encourage you to attempt this [problem](https://leetcode.com/explore/challenge/card/may-leetcoding-challenge/537/week-4-may-22nd-may-28th/) on your own before looking at my solution.

## Approach

If you are not familiar with the concept of Binary Search Tree you can read about it [here](https://www.geeksforgeeks.org/binary-search-tree-data-structure/). For every element check if it's value is greater or less than the value of the root to determine it's position.

## Solution

```python
def constructBST(root,val):
    if root:
        if val<root.val:
            if root.left:
                constructBST(root.left,val)
            else:
                root.left=TreeNode(val)
        else:
            if root.right:
                constructBST(root.right,val)
            else:
                root.right=TreeNode(val)

class Solution(object):
    def bstFromPreorder(self, preorder):
        """
        :type preorder: List[int]
        :rtype: TreeNode
        """
        root=TreeNode(preorder[0])
        for i in range(1,len(preorder)):
            constructBST(root,preorder[i])
        return root
```

### Submission Details

**Total test cases passed**: 110 / 110 \
**Runtime**: 24 ms \
**Memory Usage**: 12.8 MB 

>Note: This submission was better than 73.83% of Python3 solutions in terms of runtime! Try to come up with a better approach! :new_moon_with_face:

I would really recommend you to explore this side of the Computer Science and tune in to the journey of competitive programming to write better, cleaner, efficient and optimal code! :grinning:

If you have a better approach to this problem, or for any other queries feel free to reach out to [me](https://www.linkedin.com/in/vidhi-mody-21629a150)! :innocent: