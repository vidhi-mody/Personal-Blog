+++
title = "Kth Smallest Element in a BST: Day 20 of the May LeetCoding Challenge"
description = "My solution to the question Kth Smallest Element in a BST by LeetCode"
type = ["blogs","blog"]
tags = [
    "Competitive Coding",
    "Competitive Programming",
    "Algorithms",
    "Data Structures",
]
date = "2020-05-21"
categories = [
    "Competitive Coding",
    "Algorithms",
    "Data Structures",
]
series = ["Competitive Coding"]
[ author ]
  name = "Vidhi Mody"
+++

> *“If you can write "hello world" you can change the world”*\
> ~ Raghu Venkatesh

Day 20 of the [May LeetCoding Challenge](https://leetcode.com/explore/featured/card/may-leetcoding-challenge/) by [Leetcode](https://leetcode.com/)

### Problem definition: Kth Smallest Element in a BST

Given a binary search tree, write a function `kthSmallest` to find the **k**th smallest element in it.

> **Note**: 
> You may assume k is always valid, 1 ≤ k ≤ BST's total elements.

#### Sample Testcase 

Testcase 1

``` 
Input: root = [3,1,4,null,2], k = 1
   3
  / \
 1   4
  \
   2
Output: 1
```

Testcase 2

``` 
Input: root = [5,3,6,2,4,null,null,1], k = 3
       5
      / \
     3   6
    / \
   2   4
  /
 1
Output: 3
```
**Follow up**:

What if the BST is modified (insert/delete operations) often and you need to find the kth smallest frequently? How would you optimize the kthSmallest routine?

I highly encourage you to attempt this [problem](https://leetcode.com/explore/challenge/card/may-leetcoding-challenge/536/week-3-may-15th-may-21st/) on your own before looking at my solution.

## Solution

```cpp
/**
 * Definition for a binary tree node.
 * struct TreeNode {
 *     int val;
 *     TreeNode *left;
 *     TreeNode *right;
 *     TreeNode() : val(0), left(nullptr), right(nullptr) {}
 *     TreeNode(int x) : val(x), left(nullptr), right(nullptr) {}
 *     TreeNode(int x, TreeNode *left, TreeNode *right) : val(x), left(left), right(right) {}
 * };
 */
TreeNode* kSmallest(TreeNode* root, int& count, int k) 
{ 
    if (root == NULL) 
        return NULL; 
  
    TreeNode* left = kSmallest(root->left, count, k); 
  
    if (left != NULL) 
        return left; 
  
    count++; 
    if (count == k) 
        return root; 
   
    return kSmallest(root->right, count, k); 
}
class Solution {
public:
    int kthSmallest(TreeNode* root, int k) {
        int count = 0;
        TreeNode* res = kSmallest(root, count, k); 
        return res->val;
    }
};
```

### Submission Details

**Total test cases passed**: 91 / 91 \
**Runtime**: 28 ms \
**Memory Usage**: 24.3 MB 

>Note: This submission was better than 40.25% of cpp solutions in terms of runtime! Try to come up with a better approach! :new_moon_with_face:

I would really recommend you to explore this side of the Computer Science and tune in to the journey of competitive programming to write better, cleaner, efficient and optimal code! :grinning:

If you have a better approach to this problem, or for any other queries feel free to reach out to [me](https://www.linkedin.com/in/vidhi-mody-21629a150)! :innocent: