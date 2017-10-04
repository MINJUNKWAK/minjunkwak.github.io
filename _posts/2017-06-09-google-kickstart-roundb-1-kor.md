---
layout: single
title: "구글 Kickstart 2017 Round B Problem A 해설"
date: 2017-06-10
categories: 알고리즘
comments: true
author: MINJUN KWAK
lang: Korean
ref: googlekickstartroundbproblema
tags:
  - python
  - kickstart
  - codejam
  - algorithm
---

[Google Kickstart Round B]({{"https://code.google.com/codejam/contest/11304486/dashboard#s=p0"}}) 

주어진 집합에 대하여 모든 부분집합을 찾고, 거기에 해당하는 최소값과 최댓값을 찾은 후, 그 차이를 모두 더한다면 시간 복잡도는 ```O(2^n)```이 됩니다.

Small Test Case에는 먹힐수도 있는 방법이겠지만, 더 Large Test Case를 풀자고 하면, 문제를 보는 관점을 살짝 틀어줘야합니다.

일단 여기 예시로 나온 ```[3,6,7,9]```집합을 보시죠.

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

3+4+6+1+3+2+4+6+6+3+6 = 44. <--답
```
각 원소들이 각가 몇번이나 최댓값, 최솟값으로 설정되었는지 한번 볼까요.

|  | 3 | 6 | 7 | 9 |
|-------|-------|--------|---------|---------|
| smallest | 8 | 4 | 2 | 1 |
| largest | 1 | 2 | 4 | 8 |
| largest-smallest| -7 | -2 | 2 | 7 |

N 을 집합에 속한 원소의 갯수라고 할때.

가장 작은 원소는 최댓값이 되는 경우가 1번입니다.
그리고 최솟값이 되는 경우는 2^N번입니다.

K번재 원소가 최댓값이 되는 경우는 2^(k-1)번이고
최속값이 되는 경우는 2^(N-k+1)번입니다.

k번째 원소가 답에 미치는 영향은 ```(K번째 원소)*(2^(k-1)-2^(N-k+1)``가 되겠군요.

이제 K=1 부터 K=N까지의 경우를 모두 더하면 답이 됩니다.

시간 복잡도는 ```O(n)```가 되겠네요.

여기 아래에 파이썬으로 쓰인 제 답안이 있습니다.

[Github]({{"https://github.com/Hanuu/google_kickstart_solution/blob/master/KickStart/2017RoundB/1.py"}}) 를 클릭하시면 깃허브로 제 답안을 볼 수있습니다.

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
