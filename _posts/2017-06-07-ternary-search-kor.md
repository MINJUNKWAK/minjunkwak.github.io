---
layout: single
title: "삼분 검색(Ternary Search)"
date: 2017-06-07
categories: algorithm
comments: true
author: MINJUN KWAK
lang: Korean
ref: trenary
tags:
  - algorithm technique
  - algorithm
  - 알고리즘
  - 알고리즘 테크닉
---

일단 [위키피디아]({{https://en.wikipedia.org/wiki/Ternary_search}})에서 삼분검색의 정의에 대하여 살펴보죠.

*A ternary search algorithm is a technique in computer science for finding the minimum or maximum of a unimodal function. A ternary search determines either that the minimum or maximum cannot be in the first third of the domain or that it cannot be in the last third of the domain, then repeats on the remaining two-thirds.*
번역하자면
*삼분검색은 단봉형인 함수일때 최대,최소 값을 찾아내는 기법이다. 삼분 검색은 처음 1/3 혹은 마지막 1/3에 우리가 찾으려는 값이 없다고 알아낸 후, 남아있는 2/3를 갖고 다시 이 과정을 반복하여 답을 찾아내는 것이다.*
정도가 되겠군요.

한번 그래프로 봐볼까요?
<img src="/assets/images/tworeddots.png">

만약 제가 두 붉은 점 사이에 최소값을 구하려고 한다면, 먼저 저 사이의 구간을 3등분합니다.

<img src="/assets/images/tworedtwoblue.png">

이제 저 두 푸른 점 중에서 더 높게 있는 점을 붉은 점으로 교체하겠습니다.

<img src="/assets/images/threeredoneblue.png">

그 후에 더 가까워진 붉은 점들을 갖고 다시 반복을 합니다.
<img src="/assets/images/finaldots.png">

만약에 이 과정을 계속 반복한다면, 결국 우리가 찾던 최댓값,최솟값에 근접하게 되겠죠?

얼마나 이 과정을 반복해야 할까요?

위에 과정을 한번 반복할때마다 구간은 2/3으로 줄어듭니다.

만약에 이 과정을 n번 만큼 반복을 한다면...
```
(처음 구간)*(2/3)^n=구하려고 하는 답의 정확도
```
가 되겠지요.

여기 아래에는 삼분 검색을 활용한 알고리즘 문제 풀이가 있습니다. 참고하면 좋겠네요.
[구글 Kickstart Round B Problem 2 해설]({{"/알고리즘/google-kickstart-roundb-2-kor/"}})