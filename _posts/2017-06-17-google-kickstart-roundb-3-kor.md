---
layout: single
title: "구글 Kickstart 2017 Round B Problem C Solution"
date: 2017-06-17
categories: 알고리즘
comments: true
author: MINJUN KWAK
lang: Korean
ref: googlekickstartroundbproblemc
tags:
  - cpp
  - kickstart
  - codejam
  - algorithm
---

[Google Kickstart Round B]({{https://code.google.com/codejam/contest/11304486/dashboard#s=p2}})  

일단 Small Case부터 한번 풀어보기 시작할까요, K=1인 경우, 즉 크리스마스 트리가 단 한개일 경우입니다.

Input을 받아드리는 단계 부터 시작을 합시다.

이 문제의 tree는 모두```char```형 타입의 변수로 받아 드립니다.

green인 부분은 '#' 그리고 아닌부분은 '.'로 구분이 되어있지요.

메모리를 아끼기 위해 ```char```타입으로 받기보다 ```bool```타입으로 받는것을 추천합니다.

'.'은 0으로, '#'은 1로 설정을 하죠.

```cpp
 for(int r=0;r<N;r++){
            scanf("%s",temp);
            for(int c=0;c<M;c++){
                if(temp[c]=='.') tree[r][c]=0;
                else{ 
                    tree[r][c]=1;
                }
            }
        }
```

이제 주어진 Input값에서 가장 큰 christmas tree를 찾아봅시다.

일단 Test Case부터 분석을 한번 해볼까요.

```
..#..
.###.
#####

또는

00100
01110
11111
```
위와 같은 상황에서 어떻게 가장 큰 christmas tree를 찾아낼까요?

일단 첫번재 줄에 있는 1이 가장 큰 christmas tree의 꼭지점이라고 가정을 해봅시다. 몇개의 원소를 갖게 될까요?

높이 3에 9개의 원소를 갖고 있는 christmas tree가 되겠죠.

그렇다면 두번째 줄에 처음 나오는 1의 경우는 몇개의 원소를 갖게 될까요?

높이 2에 4개의 원소를 갖고 있는 christmas tree가 되겠네요.

주어진 모든 1에 대하여, 그 값이 christmas tree의 꼭지점이라고 가정을 하고 그 christmas tree의 원소의 갯수를 저장하는 배열을 만들면:

```int numberofgreenbyposition[100][100];```  ```numberofgreenbyposition[i][j]=(i,j)가 꼭지점일때 갖는 원소의 최대갯수```

TestCase의 경우는

```
00900
04440
11111
```
이렇게 됩니다.

조금더 계산을 간단히 하려면 ```한 christmas tree에 포함된 원소의 갯수 = (christmas tree의 높이)^2```가 되겠네요.

이럴경우 시간 복잡도는 ```O(n^2)```가 됩니다.  n= N*M = 원소의 갯수.

[Github]({{https://github.com/Hanuu/google_kickstart_solution/blob/master/KickStart/2017RoundB/3.1.cpp}}) 를 틀릭하시면 깃허브로 제 답안을 볼 수 있습니다.. 

Here's my cpp version of solution.

```cpp
#include <iostream>

using namespace std;

int N,M,K;
bool tree[100][100];
int numberofgreenbyposition[100][100];


void check(int r,int c){
    int currentr=r;
    int currentc=c;
    int height=1;
    while((0<=r+height+1-1)&&(r+height+1-1<=N-1)&&(0<=c-height-1+1)&&(c+height+1-1<=M-1)){
        for(int i=c-height-1+1;i<=c+height+1-1;i++){
            if(tree[r+height+1-1][i]==0){
                numberofgreenbyposition[r][c]=height*height;
                return;
            }
        }
        height++;
    }
    numberofgreenbyposition[r][c]=height*height;
    
    return;
}

int sol(){
    int ret=0;
    for(int r=0;r<N;r++){
        for(int c=0;c<M;c++){
            if(tree[r][c]==1){
                check(r,c);
                if(numberofgreenbyposition[r][c]>ret) ret=numberofgreenbyposition[r][c];
            }
            else numberofgreenbyposition[r][c]=0;
        }   
    }
    return ret;
}

int main(){
    
    freopen("3in.txt","r",stdin);
    freopen("3out.txt","w",stdout);
    int tc;
    scanf("%d",&tc);
    for(int nt=1;nt<=tc;nt++){
        scanf("%d %d %d",&N,&M,&K);

        char temp[100];
        for(int r=0;r<N;r++){
            scanf("%s",temp);
            for(int c=0;c<M;c++){
                if(temp[c]=='.') tree[r][c]=0;
                else{ 
                    tree[r][c]=1;
                }
            }
        }
        printf("Case #%d: %d\n",nt,sol());
        
    }
}


```
