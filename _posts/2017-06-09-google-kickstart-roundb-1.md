---
layout: single
title: "Google Kickstart 2017 Round B Problem A Solution"
date: 2017-06-09
categories: algorithm
comments: true
author: MINJUN KWAK
lang: English
ref: googlekickstartroundbproblema
tags:
  - cpp
  - kickstart
  - codejam
  - algorithm
---

[Google Kickstart Round B]({{https://code.google.com/codejam/contest/11304486/dashboard#s=p0}})  

If I were to find every subset and find its maximum, minimum value, and then subtract those two value, and every subsets' values again, the time complexity would be ```2^n```.

For small test case, this might work. However, if we want to solve the large test case as well, we have to twist the view point of the problem little bit.

Here's the sample test case provided by Google with input of ```[3,6,7,9]```
```
[3], largest-smallest = 3 - 3 = 0.
[6], largest-smallest = 6 - 6 = 0.
[7], largest-smallest = 7 - 7 = 0.
[9], largest-smallest = 9 - 9 = 0.
[3, 6], largest-smallest = 6 - 3 = 3.
[3, 7], largest-smallest = 7 - 3 = 4.
[3, 9], largest-smallest = 9 - 3 = 6.
[6, 7], largest-smallest = 7 - 6 = 1.
[6, 9], largest-smallest = 9 - 6 = 3.
[7, 9], largest-smallest = 9 - 7 = 2.
[3, 6, 7], largest-smallest = 7 - 3 = 4.
[3, 6, 9], largest-smallest = 9 - 3 = 6.
[3, 7, 9], largest-smallest = 9 - 3 = 6.
[6, 7, 9], largest-smallest = 9 - 6 = 3.
[3, 6, 7, 9], largest-smallest = 9 - 3 = 6.

3+4+6+1+3+2+4+6+6+3+6 = 44. <--answer
```

I am going to count how many times each element was regarded as largest, or smallest.

|  | 3 | 6 | 7 | 9 |
|-------|-------|--------|---------|---------|
| smallest | 8 | 4 | 2 | 1 |
| largest | 1 | 2 | 4 | 8 |