+++
title = "Majority Element: Day 6 of the May LeetCoding Challenge"
description = ""
type = ["blogs","blog"]
tags = [
    "Competitive Coding",
    "Competitive Programming",
    "Algorithms",
    "Data Structures",
]
date = "2020-05-07"
categories = [
    "Competitive Coding",
    "Algorithms",
    "Data Structures",
]
series = ["Competitive Coding"]
[ author ]
  name = "Vidhi Mody"
+++
> *“Sometimes it pays to stay in bed on Monday, rather than spending the rest of the week debugging Monday's code.”*\
>~Dan Salomon


Day 6 of the [May LeetCoding Challenge](https://leetcode.com/explore/featured/card/may-leetcoding-challenge/) by [Leetcode](https://leetcode.com/)

If you were to see 1% increases in your programming abilities by the day, you would be twice as good in 72 days by simple compound interest. Take things slow, there is nothing better than gradual progress! Give things sometime, you'll get there!

### Problem definition: Majority Element

Given an array of size n, find the majority element. The majority element is the element that appears **more than** `⌊ n/2 ⌋` times. 

> Note: You may assume that the array is non-empty and the majority element always exist in the array.

#### Sample Testcase 

Testcase 1
```
Input: [3,2,3]
Output: 3
```

Testcase 2
```
Input: [2,2,1,1,1,2,2]
Output: 2
```

I highly encourage you to attempt this [problem](https://leetcode.com/explore/featured/card/may-leetcoding-challenge/534/week-1-may-1st-may-7th/) on your own before looking at my solution.

## Approach

Iteratively traverse through the numbers, and create a dictionary to store the occurence of each number of the string. \
Next, find the key of the element containing the maximum value and return it.

## Solution

```python
class Solution(object):
    def majorityElement(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        numbers = {} 
  
        for i in nums: 
            if i in numbers: 
                numbers[i] += 1
            else: 
                numbers[i] = 1
        majority_element = max(numbers, key=numbers.get) 
        return majority_element
```

### Submission Details

**Total test cases passed**: 46 / 46 \
**Runtime**: 152 ms \
**Memory Usage**: 14.1 MB 

>Note: This submission was better than 74.11% of Python3 solutions in terms of runtime. Try to come up with a solution that is more optimal! :new_moon_with_face: 

I would really recommend you to explore this side of the Computer Science and tune in to the journey of competitive programming to write better, cleaner, efficient and optimal code! :grinning:

If you have a better approach to this problem, or for any other queries feel free to reach out to [me]((https://www.linkedin.com/in/vidhi-mody-21629a150))! :innocent:
