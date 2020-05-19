+++
title = "Check If It Is a Straight Line: Day 8 of the May LeetCoding Challenge"
description = ""
type = ["blogs","blog"]
tags = [
    "Competitive Coding",
    "Competitive Programming",
    "Algorithms",
    "Data Structures",
]
date = "2020-05-09"
categories = [
    "Competitive Coding",
    "Algorithms",
    "Data Structures",
]
series = ["Competitive Coding"]
[ author ]
  name = "Vidhi Mody"
+++
> *“Programming isn't about what you know; it's about what you can figure out.”*\
>~Chris Pine


Day 8 of the [May LeetCoding Challenge](https://leetcode.com/explore/featured/card/may-leetcoding-challenge/) by [Leetcode](https://leetcode.com/)

Learning something new is always an advantage! There is no wrong method when it comes to learning, find a way that suits you the best. Learn by reading a book, attend online seminars or signup for an online course but make sure to challenge yourself.

*If not now, then when?* The lockdown has given you an opportunity to better yourself, do something positive for your personal growth and development. 

{{<center src="/img/day8.gif" alt="learn">}}

### Problem definition: Check If It Is a Straight Line

You are given an array `coordinates`, `coordinates[i] = [x, y]`, where `[x, y]` represents the coordinate of a point. Check if these points make a straight line in the XY plane.

> Constraints:
> - 2 <= coordinates.length <= 1000
> - coordinates[i].length == 2
> - -10^4 <= coordinates[i][0], coordinates[i][1] <= 10^4
> - coordinates contains no duplicate point.

#### Sample Testcase 

Testcase 1
![line1](/img/line1.png) 
```
Input: coordinates = [[1,2],[2,3],[3,4],[4,5],[5,6],[6,7]]
Output: true
```

Testcase 2
![line2](/img/line2.png) 
```
Input: coordinates = [[1,1],[2,2],[3,4],[4,5],[5,6],[7,7]]
Output: false
```

> ### Hints
> - If there're only 2 points, return true.
> - Check if all other points lie on the line defined by the first 2 points.
> - Use cross product to check collinearity.


I highly encourage you to attempt this [problem](https://leetcode.com/explore/challenge/card/may-leetcoding-challenge/535/week-2-may-8th-may-14th/) on your own before looking at my solution.

## Approach

Obtain the equation of the line that passes through the first two points. ( *if the input contains only two points, return `True`* ) Starting the iteration from the third point, check if the point lies on the equation computed previously. As soon as a point does not satisfy the equation, return `False`.

## Solution

```python
class Solution:
    def checkStraightLine(self, coordinates: List[List[int]]) -> bool:
        if(len(coordinates)==2):
            return True
        else:
            a = coordinates[1][1] - coordinates[0][1] 
            b = coordinates[0][0] - coordinates[1][0]  
            c = a*(coordinates[0][0]) + b*(coordinates[0][1]) 
            for i in range(2,len(coordinates)):
                    if((a*coordinates[i][0] + b*coordinates[i][1])!=c):
                        return False   
            return True
```

### Submission Details

**Total test cases passed**: 66 / 66 \
**Runtime**: 56 ms \
**Memory Usage**: 13.9 MB 

>Note: This submission was better than 92.73% of Python3 solutions in terms of runtime. Try to come up with a solution that is more optimal! :new_moon_with_face: 

I would really recommend you to explore this side of the Computer Science and tune in to the journey of competitive programming to write better, cleaner, efficient and optimal code! :grinning:

If you have a better approach to this problem, or for any other queries feel free to reach out to [me]((https://www.linkedin.com/in/vidhi-mody-21629a150))! :innocent:
