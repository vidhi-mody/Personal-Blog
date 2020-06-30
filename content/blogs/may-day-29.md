+++
title = "Course Schedule: Day 29 of the May LeetCoding Challenge"
description = "My solution to the question Course Schedule by LeetCode"
type = ["blogs","blog"]
tags = [
    "Competitive Coding",
    "Competitive Programming",
    "Algorithms",
    "Data Structures",
]
date = "2020-05-30"
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

Day 29 of the [May LeetCoding Challenge](https://leetcode.com/explore/featured/card/may-leetcoding-challenge/) by [Leetcode](https://leetcode.com/)

### Problem definition: Course Schedule

There are a total of `numCourses` courses you have to take, labeled from `0` to `numCourses-1`.

Some courses may have prerequisites, for example to take course 0 you have to first take course 1, which is expressed as a pair: `[0,1]`

Given the total number of courses and a list of prerequisite **pairs**, is it possible for you to finish all courses?

#### Sample Testcase 

Testcase 1
``` 
Input: numCourses = 2, prerequisites = [[1,0]]
Output: true
Explanation: There are a total of 2 courses to take. 
To take course 1 you should have finished course 0. So it is possible.
```

Testcase 2
```
Input: numCourses = 2, prerequisites = [[1,0],[0,1]]
Output: false
Explanation: There are a total of 2 courses to take.
To take course 1 you should have finished course 0, and to take course 0 you should also have finished course 1. So it is impossible.
```

> **Constraints**:
> - The input prerequisites is a graph represented by **a list of edges**, not adjacency matrices. Read more about [how a graph is represented](https://www.khanacademy.org/computing/computer-science/algorithms/graph-representation/a/representing-graphs).
> - You may assume that there are no duplicate edges in the input prerequisites.
> - `1 <= numCourses <= 10^5`

I highly encourage you to attempt this [problem](https://leetcode.com/explore/challenge/card/may-leetcoding-challenge/538/week-5-may-29th-may-31st/) on your own before looking at my solution.

:bulb: **Hints:**
1. This problem is equivalent to finding if a cycle exists in a directed graph. If a cycle exists, no topological ordering exists and therefore it will be impossible to take all courses.
2. [Topological Sort via DFS](https://www.coursera.org/specializations/algorithms) - A great video tutorial (21 minutes) on Coursera explaining the basic concepts of Topological Sort.
3. Topological sort could also be done via [BFS](https://en.wikipedia.org/wiki/Topological_sorting#Algorithms).

## Approach

Consider each course as a node and make an edge from the prerequisite course to the current course. Next, count the in-degree and out-degree of each node. \
(*Note: For a directed graph and a vertex , the Out-Degree of refers to the number of arcs incident from . That is, the number of arcs directed away from the vertex . The In-Degree of refers to the number of arcs incident to . That is, the number of arcs directed towards the vertex. Read more about it [here.](http://mathonline.wikidot.com/out-degree-sequence-and-in-degree-sequence)*) \
Next, append all nodes with in-degree equal to 0 in a stack. When a node is popped from the child reduce the child's in-degree by one and increment the counter for every node popped. \
If counter is equal to the no. of courses a  cycle does not exist. Return `true`.


## Solution

```python
class Solution(object):
    def canFinish(self, numCourses, prerequisites):
        """
        :type numCourses: int
        :type prerequisites: List[List[int]]
        :rtype: bool
        """
        inDegree={}
        for i in range(numCourses):
            inDegree[i]=0
            
        outDegree = collections.defaultdict(list)
        for a, b in prerequisites:
            inDegree[b] += 1
            outDegree[a].append(b)
            
        count = 0
        visited = []
        for i in range(numCourses):
            if inDegree[i] == 0:
                visited.append(i)

        while(visited):
            curr = visited.pop()
            count += 1
            for child in outDegree[curr]:
                inDegree[child] -= 1
                if inDegree[child] == 0:
                    visited.append(child)
            
        return count == numCourses
```

### Submission Details

**Total test cases passed**: 46 / 46 \
**Runtime**: 76 ms \
**Memory Usage**: 14.2 MB 

>Note: This submission was better than 94.50% of Python3 solutions in terms of runtime! Try to come up with a better approach! :new_moon_with_face:

I would really recommend you to explore this side of the Computer Science and tune in to the journey of competitive programming to write better, cleaner, efficient and optimal code! :grinning:

If you have a better approach to this problem, or for any other queries feel free to reach out to [me](https://www.linkedin.com/in/vidhi-mody-21629a150)! :innocent: