---
layout: single
title: "Google Kickstart 2017 Round B Problem B Solution"
date: 2017-06-07
categories: algorithm
comments: true
author: MINJUN KWAK
lang: English
ref: googlekickstartroundbproblemb
tags:
  - cpp
  - kickstart
  - codejam
  - algorithm
---

[Google Kickstart Round B]({{https://code.google.com/codejam/contest/11304486/dashboard#s=p1}})  

If we were to use the 'brute-force' in this problem, we would be inserting numbers from -1000.00 to 1000.00 with 0.01 interval. 

The time complexity would be ```O(n^3)```. Given n=100000, we might not be able to solve the problem in time.

We need a better method to find the minimum value in this scenario!

Let us analysis the problem further more, if we were to put -1000.00 to 1000.00, what would be the value look like?

```
Σ max(|X-Xi|, |Y-Yi|)*Wi

```
To save more trouble, let's look at the ```x``` first, let us forget about the ```y```.
```
Σ |X-Xi|
```
Here's what the graph is going to look like

<img src="/assets/images/absolutegraph.png">

It is a convex graph with one minimum value.

The question now is, how to find that minimum value with the least effort?

May I introduce you the [Ternary Search]({{"/algorithm/ternary-search/"}})! The mighty solution to finding minimum/maximum value when graph is convex or concave.

How many times should we repeat the process? Since considered our value is correct if it is within an absolute or relative error of ```10^-6``` of the correct answer, 100 times would be good.

Every time we complete one cycle of [Ternary Search]({{"/algorithm/ternary-search/"}}), the interval is reduced by 2/3. If we repeat the process 100 times, ```2000*(2/3)^100=4.191930E-15``` it seems more than reasonable.

The time complexity for using [Ternary Search]({{"/algorithm/ternary-search/"}}) is ```O(n*(logn)^2)```

Here's the full code in cpp

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

//setting y value using ternary search
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

//setting x value first using ternary search
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