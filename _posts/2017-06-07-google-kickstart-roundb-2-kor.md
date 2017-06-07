---
layout: single
title: "구글 Kickstart Round B Problem B 해설"
date: 2017-06-07
categories: 알고리즘
comments: true
author: MINJUN KWAK
lang: Korean
ref: googlekickstartroundbproblemb
tags:
  - cpp
  - kickstart
  - codejam
  - algorithm
---

[Google Kickstart Round B]({{https://code.google.com/codejam/contest/11304486/dashboard#s=p1}})

완전탐색을 사용하여 문제를 풀수도 있겠지만 -1000.00 부터 1000.00까지 모든 숫자들을 0.01간격으로 집어넣는다는것은 자살행위로 보입니다.

시간 복잡도가 ```O(n^3)```(n=100000)인 상황에서 문제를 시간안에 푸는것이 불가능 해보이는군요.

주어진 식의 최소값을 찾는데 조금 더 효율적인 방법을 찾을 필요가 있어보입니다.

문제를 조금 더 자세히 살펴볼까요? 일단 주어진 식을 다시 관찰해봅시다.
```
Σ max(|X-Xi|, |Y-Yi|)*Wi

```
문제를 좀 간단하게 해석하기위해 ```x```값만을 살펴봅시다.
```
Σ |X-Xi|
```
위 식을 그래프로 한번 나타내볼까요

<img src="/assets/images/absolutegraph.png">

우리가 쉽게 떠올릴수있는 오목함수의 모양을 하고있습니다.

그렇다면, 주어진 구간안에서 어떻게 가장 쉬운 방법으로 최소값을 구할수 있을까요?

[삼분 검색(Ternary Search)]({{"/algorithm/ternary-search/"}})을 사용하면 좋을 것같습니다.

[삼분 검색(Ternary Search)]({{"/algorithm/ternary-search/"}})을 사용한더면 몇번이나 반복하는게 이상적일까요? 문제에서는 답이 오차범위 ```10^-6```안에서는 인정되기때문에 100번 정도 반복을 하면 아주 안전 할 것 같군요.

우리가 [삼분 검색(Ternary Search)]({{"/algorithm/ternary-search/"}})을 반복할때마다, 구간은 2/3씩 줄어듭니다. 이걸 100번 반복한다고 보면 ```2000*(2/3)^100=4.191930E-15``` 정도가 나오는데 오차범위한참 안에 있겠네요.

[삼분 검색(Ternary Search)]({{"/algorithm/ternary-search/"}})을 이용헸을때 시간 복잡도는 ```O(n*(logn)^2)```가 됩니다.

아래는 C++로 구현한 코드입니다.

```cpp
#include <iostream>
#include <cmath>
using namespace std;

double X[10000],Y[10000],W[10000];

//given x and y, returning the sum of the value
double sum(double x,double y,int n){
    double ret=0;
    for(int i=0;i<n;i++){
        ret+=max(abs(x-X[i]),abs(y-Y[i]))*W[i];
    }
    return ret;
}

//setting y value
double valueof(double x,int n){
    double hi=1000;
    double lo=-1000;
    for(int i=0;i<100;i++){
        double lposition=(lo*2+hi)/3;
        double rposition=(lo+2*hi)/3;
        double l=sum(x,lposition,n);
        double r=sum(x,rposition,n);
        if(l<=r) hi=rposition;
        else lo=lposition;
    }
    return sum(x,lo,n);
}

//setting x value first
double sol(int n){
    double hi=1000;
    double lo=-1000;
    for(int i=0;i<100;i++){
        double lposition=(lo*2+hi)/3;
        double rposition=(lo+2*hi)/3;
        double l=valueof(lposition,n);
        double r=valueof(rposition,n);
        if(l<=r) hi=rposition;
        else lo=lposition;
    }
    return valueof(lo,n);
}


int main(){
    
    int tc;
    scanf("%d",&tc);
    int n;
    for(int cn=1;cn<=tc;cn++){
        scanf("%d",&n);
        for(int vn=0;vn<n;vn++){
            scanf("%lf %lf %lf",X+vn,Y+vn,W+vn);
            // printf("%lf %lf %lf\n",X[vn],Y[vn],W[vn]);
        }
        printf("Case #%d: %lf\n",cn,sol(n));
    }
    
}
```