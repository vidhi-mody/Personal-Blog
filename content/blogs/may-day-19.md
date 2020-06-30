+++
title = "Online Stock Span: Day 19 of the May LeetCoding Challenge"
description = "My solution to the question Online Stock Span by LeetCode"
type = ["blogs","blog"]
tags = [
    "Competitive Coding",
    "Competitive Programming",
    "Algorithms",
    "Data Structures",
]
date = "2020-05-20"
categories = [
    "Competitive Coding",
    "Algorithms",
    "Data Structures",
]
series = ["Competitive Coding"]
[ author ]
  name = "Vidhi Mody"
+++

> *“Programming is breaking of one big impossible task into several very small possible tasks.”*\
> ~ Jazzwant

Day 19 of the [May LeetCoding Challenge](https://leetcode.com/explore/featured/card/may-leetcoding-challenge/) by [Leetcode](https://leetcode.com/)

### Problem definition: Online Stock Span

Write a class `StockSpanner` which collects daily price quotes for some stock, and returns the span of that stock's price for the current day.

The span of the stock's price today is defined as the maximum number of consecutive days (starting from today and going backwards) for which the price of the stock was less than or equal to today's price.

For example, if the price of a stock over the next 7 days were `[100, 80, 60, 70, 60, 75, 85]`, then the stock spans would be `[1, 1, 1, 2, 1, 4, 6]`.

> **Note**: 
>   1. Calls to StockSpanner.next(int price) will have 1 <= price <= 10^5.
>   2. There will be at most `10000` calls to `StockSpanner.next` per test case.
>   3. There will be at most `150000` calls to `StockSpanner.next` across all test cases.
>   4. The total time limit for this problem has been reduced by 75% for C++, and 50% for all other languages.

#### Sample Testcase 

Testcase 1

``` 
Input: ["StockSpanner","next","next","next","next","next","next","next"], [[],[100],[80],[60],[70],[60],[75],[85]]
Output: [null,1,1,1,2,1,4,6]
Explanation: 
First, S = StockSpanner() is initialized.  Then:
S.next(100) is called and returns 1,
S.next(80) is called and returns 1,
S.next(60) is called and returns 1,
S.next(70) is called and returns 2,
S.next(60) is called and returns 1,
S.next(75) is called and returns 4,
S.next(85) is called and returns 6.

Note that (for example) S.next(75) returned 4, because the last 4 prices
(including today's price of 75) were less than or equal to today's price.
```

I highly encourage you to attempt this [problem](https://leetcode.com/explore/challenge/card/may-leetcoding-challenge/536/week-3-may-15th-may-21st/) on your own before looking at my solution.

## Solution

```python
class StockSpanner:
    def __init__(self):
        self.stacks = []

    def next(self, price: int) -> int:
        n = 1
        while self.stacks:
            val, num = self.stacks[-1]
            if price < val:
                self.stacks.append((price, n))
                return n
            else:
                n += num
                self.stacks.pop()
        self.stacks.append((price, n))
        
        return n
```

### Submission Details

**Total test cases passed**: 99 / 99 \
**Runtime**: 712 ms \
**Memory Usage**: 18.5 MB 

>Note: This submission was better than 8.67% of Python3 solutions in terms of runtime! Try to come up with a better approach! :worried:

I would really recommend you to explore this side of the Computer Science and tune in to the journey of competitive programming to write better, cleaner, efficient and optimal code! :grinning:

If you have a better approach to this problem, or for any other queries feel free to reach out to [me](https://www.linkedin.com/in/vidhi-mody-21629a150)! :innocent: