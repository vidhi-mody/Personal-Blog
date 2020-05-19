+++
title = "Flood Fill: Day 11 of the May LeetCoding Challenge"
description = ""
type = ["blogs","blog"]
tags = [
    "Competitive Coding",
    "Competitive Programming",
    "Algorithms",
    "Data Structures",
]
date = "2020-05-12"
categories = [
    "Competitive Coding",
    "Algorithms",
    "Data Structures",
]
series = ["Competitive Coding"]
[ author ]
  name = "Vidhi Mody"
+++

> *“Most improved things can be improved.”* \
> ~Mokokoma Mokhonoana

Day 11 of the [May LeetCoding Challenge](https://leetcode.com/explore/featured/card/may-leetcoding-challenge/) by [Leetcode](https://leetcode.com/)

### Problem definition: Flood Fill

An `image` is represented by a 2-D array of integers, each integer representing the pixel value of the image (from 0 to 65535).

Given a coordinate `(sr, sc)` representing the starting pixel (row and column) of the flood fill, and a pixel value `newColor`, "flood fill" the image.

To perform a "flood fill", consider the starting pixel, plus any pixels connected 4-directionally to the starting pixel of the same color as the starting pixel, plus any pixels connected 4-directionally to those pixels (also with the same color as the starting pixel), and so on. Replace the color of all of the aforementioned pixels with the newColor.

At the end, return the modified image.

> Note: 
> - The length of image and image[0] will be in the range [1, 50].
> - The given starting pixel will satisfy 0 <= sr < image.length and 0 <= sc < image[0].length.
> - The value of each color in image[i][j] and newColor will be an integer in [0, 65535].


#### Sample Testcase 

Testcase 1

``` 
image = [[1,1,1],[1,1,0],[1,0,1]]
sr = 1, sc = 1, newColor = 2
Output: [[2,2,2],[2,2,0],[2,0,1]]
Explanation: 
From the center of the image (with position (sr, sc) = (1, 1)), all pixels connected 
by a path of the same color as the starting pixel are colored with the new color.
Note the bottom corner is not colored 2, because it is not 4-directionally connected
to the starting pixel.
```
> Hint: \
> Write a recursive function that paints the pixel if it's the correct color, then recurses on neighboring pixels.

I highly encourage you to attempt this [problem](https://leetcode.com/explore/challenge/card/may-leetcoding-challenge/535/week-2-may-8th-may-14th/) on your own before looking at my solution.

## Approach

Keep checking the 4 neighbouring pixels recursively with the oldColor and set the color to newColor.

{{<center src="/img/flood_fill.gif" alt="Flood Fill">}}

## Solution

```python
class Solution:
    def floodFill(self, image: List[List[int]], sr: int, sc: int, newColor: int) -> List[List[int]]:
        if(len(image) == 0 or len(image[0]) == 0 or image[sr][sc] == newColor):
            return image
        oldColor = image[sr][sc]

        def fill(i, j):
            if(0 <= i < len(image) and 0 <= j < len(image[0]) and image[i][j] == oldColor):
                image[i][j] = newColor
                fill(i, j-1)
                fill(i, j+1)
                fill(i-1, j)
                fill(i+1, j)           
        fill(sr, sc)
        
        return image
```

### Submission Details

**Total test cases passed**: 277 / 277 \
**Runtime**: 80 ms \
**Memory Usage**: 14.1 MB 

>Note: This submission was better than 55.06% of Python3 solutions in terms of runtime! Try to come up with a better approach! :new_moon_with_face: 

I would really recommend you to explore this side of the Computer Science and tune in to the journey of competitive programming to write better, cleaner, efficient and optimal code! :grinning:

If you have a better approach to this problem, or for any other queries feel free to reach out to [me]((https://www.linkedin.com/in/vidhi-mody-21629a150))! :innocent:
