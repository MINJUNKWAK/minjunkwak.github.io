---
layout: single
title: "Ternary Search"
date: 2017-06-07
categories: algorithm
comments: true
author: MINJUN KWAK
lang: English
ref: trenary
tags:
  - algorithm technique
  - algorithm
---

Here's the definition of Ternary Search in [Wikipedia]({{"https://en.wikipedia.org/wiki/Ternary_search"}})

*A ternary search algorithm is a technique in computer science for finding the minimum or maximum of a unimodal function. A ternary search determines either that the minimum or maximum cannot be in the first third of the domain or that it cannot be in the last third of the domain, then repeats on the remaining two-thirds.*

Let me show you how this works in graph.

<img src="/assets/images/tworeddots.png">

If I were to find the minimum value between two red dots in this graph, I will divide the given length into 3 parts with same intervals.

<img src="/assets/images/tworedtwoblue.png">

Now between the two blue dots, I will replace the higher one with the red dot.

<img src="/assets/images/threeredoneblue.png">

Then, I will repeat the process with two red dots that are closer than before.

<img src="/assets/images/finaldots.png">

If I repeat this process enough, it will eventually get closer to the minium/maximum value that I was looking for.

How many times whould we repeat? 

Every time we repeat the process, the interval is multipied by 2/3.

So n= times that require to repeat the process,

```
(Intial Interval)*(2/3)^n=accuracy of the value
```

Here's the example of using Ternary Search in a real problem.
[Google Kickstart Round B Problem 2]({{"/algorithm/google-kickstart-roundb-2/"}})
