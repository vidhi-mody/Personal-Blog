+++
title = "Count Square Submatrices with All Ones: Day 21 of the May LeetCoding Challenge"
description = "My solution to the question Count Square Submatrices with All Ones by LeetCode"
type = ["blogs","blog"]
tags = [
    "Competitive Coding",
    "Competitive Programming",
    "Algorithms",
    "Data Structures",
]
date = "2020-05-22"
categories = [
    "Competitive Coding",
    "Algorithms",
    "Data Structures",
]
series = ["Competitive Coding"]
[ author ]
  name = "Vidhi Mody"
+++

> *"Data dominates. If you've chosen the right data structures and organized things well, the algorithms will almost always be self-evident. Data structures, not algorithms, are central to programming.”*\
> ~ Rob Pike

Day 21 of the [May LeetCoding Challenge](https://leetcode.com/explore/featured/card/may-leetcoding-challenge/) by [Leetcode](https://leetcode.com/)

### Problem definition: Count Square Submatrices with All Ones

Given a `m * n` matrix of ones and zeros, return how many **square** submatrices have all ones.

#### Sample Testcase 

Testcase 1

``` 
Input: matrix =
[
  [0,1,1,1],
  [1,1,1,1],
  [0,1,1,1]
]
Output: 15
Explanation: 
There are 10 squares of side 1.
There are 4 squares of side 2.
There is  1 square of side 3.
Total number of squares = 10 + 4 + 1 = 15.
```

Testcase 2

``` 
Input: matrix = 
[
  [1,0,1],
  [1,1,0],
  [1,1,0]
]
Output: 7
Explanation: 
There are 6 squares of side 1.  
There is 1 square of side 2. 
Total number of squares = 6 + 1 = 7.
```

**Constraints:**
- 1 <= arr.length <= 300
- 1 <= arr[0].length <= 300
- 0 <= arr[i][j] <= 1

I highly encourage you to attempt this [problem](https://leetcode.com/explore/challenge/card/may-leetcoding-challenge/536/week-3-may-15th-may-21st/) on your own before looking at my solution.

## Solution

```python
class Solution(object):
    def countSquares(self, matrix):
        """
        :type matrix: List[List[int]]
        :rtype: int
        """
        answer = 0
        lenCol = len(matrix)
        if(lenCol==0):
            return answer
        lenRow = len(matrix[0])
        for i in range(lenCol):
            for j in range(lenRow):
                if(matrix[i][j]==0):
                    continue
                if(i==0 or j==0):
                    answer = answer + 1
                    continue
                min1 = min(matrix[i-1][j-1], matrix[i][j-1],matrix[i-1][j])
                matrix[i][j] += min1
                answer += matrix[i][j]
        return answer
```

### Submission Details

**Total test cases passed**: 32 / 32 \
**Runtime**: 792 ms \
**Memory Usage**: 14.8 MB 

>Note: This submission was better than 25.06% of Python3 solutions in terms of runtime! Try to come up with a better approach! :new_moon_with_face:

I would really recommend you to explore this side of the Computer Science and tune in to the journey of competitive programming to write better, cleaner, efficient and optimal code! :grinning:

If you have a better approach to this problem, or for any other queries feel free to reach out to [me](https://www.linkedin.com/in/vidhi-mody-21629a150)! :innocent: