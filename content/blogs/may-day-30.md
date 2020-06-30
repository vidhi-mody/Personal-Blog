+++
title = "K Closest Points to Origin: Day 30 of the May LeetCoding Challenge"
description = "My solution to the question K Closest Points to Origin by LeetCode"
type = ["blogs","blog"]
tags = [
    "Competitive Coding",
    "Competitive Programming",
    "Algorithms",
    "Data Structures",
]
date = "2020-05-31"
categories = [
    "Competitive Coding",
    "Algorithms",
    "Data Structures",
]
series = ["Competitive Coding"]
[ author ]
  name = "Vidhi Mody"
+++

> *“Data dominates. If you've chosen the right data structures and organized things well, the algorithms will almost always be self-evident. Data structures, not algorithms, are central to programming.”* \
> ~ Rob Pike

Day 30 of the [May LeetCoding Challenge](https://leetcode.com/explore/featured/card/may-leetcoding-challenge/) by [Leetcode](https://leetcode.com/)

### Problem definition: K Closest Points to Origin

We have a list of `points` on the plane.  Find the `K` closest points to the origin `(0, 0)`.

(Here, the distance between two points on a plane is the Euclidean distance.)

You may return the answer in any order.  The answer is guaranteed to be unique (except for the order that it is in.)

#### Sample Testcase 

Testcase 1
``` 
Input: points = [[1,3],[-2,2]], K = 1
Output: [[-2,2]]
Explanation: 
The distance between (1, 3) and the origin is sqrt(10).
The distance between (-2, 2) and the origin is sqrt(8).
Since sqrt(8) < sqrt(10), (-2, 2) is closer to the origin.
We only want the closest K = 1 points from the origin, so the answer is just [[-2,2]].
```

Testcase 2
```
Input: points = [[3,3],[5,-1],[-2,4]], K = 2
Output: [[3,3],[-2,4]]
(The answer [[-2,4],[3,3]] would also be accepted.)
```

> **Note**:
> 1. 1 <= K <= points.length <= 10000
> 2. -10000 < points[i][0] < 10000
> 3. -10000 < points[i][1] < 10000

I highly encourage you to attempt this [problem](https://leetcode.com/explore/challenge/card/may-leetcoding-challenge/538/week-5-may-29th-may-31st/) on your own before looking at my solution.

## Approach

Calculate the distance of each point from the origin and save it in a dictionary with the key as the index of the point.
Next sort the dictionary by value. Then, depending on the value of `K` fetch the first K index of the sorted dictionary and return the points with those index as your answer.


## Solution

```python
class Solution(object):
    def kClosest(self, points, K):
        """
        :type points: List[List[int]]
        :type K: int
        :rtype: List[List[int]]
        """
        distance = {}
        answer = []
        if(K==len(points)):
            return points
        for i in range(len(points)):
            distance[i] = math.sqrt( (points[i][0]**2)+(points[i][1]**2) )
        sorted_distance = sorted(distance.items(), key=lambda kv: kv[1])
        
        for i in range(K):
            answer.append(points[sorted_distance[i][0]])
            
        return answer
```

### Submission Details

**Total test cases passed**: 83 / 83 \
**Runtime**: 604 ms \
**Memory Usage**: 19.9 MB 

>Note: This submission was better than 78.39% of Python3 solutions in terms of runtime! Try to come up with a better approach! :new_moon_with_face:

I would really recommend you to explore this side of the Computer Science and tune in to the journey of competitive programming to write better, cleaner, efficient and optimal code! :grinning:

If you have a better approach to this problem, or for any other queries feel free to reach out to [me](https://www.linkedin.com/in/vidhi-mody-21629a150)! :innocent: