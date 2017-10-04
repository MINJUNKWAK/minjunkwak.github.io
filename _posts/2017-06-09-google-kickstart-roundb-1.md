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
  - python
  - kickstart
  - codejam
  - algorithm
---

[Google Kickstart Round B]({{"https://code.google.com/codejam/contest/11304486/dashboard#s=p0"}})  

If I were to find every subset and find its maximum, minimum value, and then subtract those two value, and every subsets' values again, the time complexity would be ```O(2^n)```.

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
| largest-smallest| -7 | -2 | 2 | 7 |

N being the number of elements,

First element can only be the largest 1 time
and it can only be the smallest elements 2^N times

The Kth element can only be the largest 2^(k-1) times
and it can only be the smallest elements 2^(N-k+1) times.

So the total contribution of Kth element to the answer is ```(Kth element)*(2^(k-1)-2^(N-k+1)```

All we have to do is add from k=1 to k=N. With the time complexity being ```O(N)```

Here's my python code to the problem.

Click [Github]({{"https://github.com/Hanuu/google_kickstart_solution/blob/master/KickStart/2017RoundB/1.py"}}) to view the solution in Github. 
```python

f= open("1in.txt").read().split("\n")
writeF=open("1out.txt","w")


def gettotal(N,K):
    total=0
    for i in range(0,N):
        total+=(-2**(N-i-1)+2**(i))*int(K[i])
    return total%(10**9+7)
    
number=1
for i in range(1,2*int(f[0])+2,2):
    N=int(f[i])
    K=f[i+1].split(" ")
    
    answer=gettotal(N,K)
    print("Case #%d: %d" %(number,answer))
    
    writeF.write("Case #%d: %d\n" %(number,answer))
    number+=1
f.close()
writeF.close()
```
