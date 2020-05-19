+++
title = "Odd Even Linked List: Day 16 of the May LeetCoding Challenge"
description = ""
type = ["blogs","blog"]
tags = [
    "Competitive Coding",
    "Competitive Programming",
    "Algorithms",
    "Data Structures",
]
date = "2020-05-17"
categories = [
    "Competitive Coding",
    "Algorithms",
    "Data Structures",
]
series = ["Competitive Coding"]
[ author ]
  name = "Vidhi Mody"
+++

> *“Some of the best programming is done on paper, really. Putting it into the computer is just a minor detail.”*\
> ~ Max Kanat-Alexander

Day 16 of the [May LeetCoding Challenge](https://leetcode.com/explore/featured/card/may-leetcoding-challenge/) by [Leetcode](https://leetcode.com/)

### Problem definition: Odd Even Linked List

Given a singly linked list, group all odd nodes together followed by the even nodes. Please note here we are talking about the node number and not the value in the nodes.

You should try to do it in place. The program should run in O(1) space complexity and O(nodes) time complexity.

> **Note**: 
> - The relative order inside both the even and odd groups should remain as it was in the input.
> - The first node is considered odd, the second node even and so on ...

#### Sample Testcase 

Testcase 1

``` 
Input: 1->2->3->4->5->NULL
Output: 1->3->5->2->4->NULL
```

Testcase 2

``` 
Input: 2->1->3->5->6->4->7->NULL
Output: 2->3->6->7->1->5->4->NULL
```

I highly encourage you to attempt this [problem](https://leetcode.com/explore/challenge/card/may-leetcoding-challenge/536/week-3-may-15th-may-21st/) on your own before looking at my solution.

## Approach

In simple terms, we are suppose to link the head of odd to `even->next` which will be the next odd term. Similarly we are to link the head of even to `odd->next`. Continue this till `odd->next` or `even->next == NULL`. Then connect the last odd element to the head of the first even element. \
PS: Don't forget to tackle corner cases like:
- an empty list
- a list with only one element
- a lit with only two elements

## Solution

```cpp
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode() : val(0), next(nullptr) {}
 *     ListNode(int x) : val(x), next(nullptr) {}
 *     ListNode(int x, ListNode *next) : val(x), next(next) {}
 * };
 */
class Solution {
public:
    ListNode* oddEvenList(ListNode* head) {
        if (head == NULL)  
            return NULL;  
        if (head->next == NULL)
            return head;
        if(head->next->next == NULL)
            return head;
        ListNode *odd = head;  
        ListNode *even = head->next;   
        ListNode *firstEven = even;  

        while (true)  
        {  
            if (!odd || !even || !(even->next))  
            {  
                odd->next = firstEven;  
                break;  
            }  

            odd->next = even->next;  
            odd = even->next;  

            if (odd->next == NULL)  
            {  
                even->next = NULL;  
                odd->next = firstEven;  
                break;  
            }  

            even->next = odd->next;  
            even = odd->next;  
        }  

        return head;

    }
};
```

### Submission Details

**Total test cases passed**: 71 / 71 \
**Runtime**: 20 ms \
**Memory Usage**: 9.8 MB 

>Note: This submission was better than 58.38% of cpp solutions in terms of runtime! Try to come up with a better approach! :new_moon_with_face: 

I would really recommend you to explore this side of the Computer Science and tune in to the journey of competitive programming to write better, cleaner, efficient and optimal code! :grinning:

If you have a better approach to this problem, or for any other queries feel free to reach out to [me](https://www.linkedin.com/in/vidhi-mody-21629a150)! :innocent:
