---
layout: single
title: "Google Kickstart 2017 Round B Problem C Solution"
date: 2017-06-15
categories: algorithm
comments: true
author: MINJUN KWAK
lang: English
ref: googlekickstartroundbproblemc
tags:
  - cpp
  - kickstart
  - codejam
  - algorithm
---

[Google Kickstart Round B]({{"https://code.google.com/codejam/contest/11304486/dashboard#s=p2"}})  

Let's try to solve the Small Case first, being K=1, we only have to find one christmas tree.

Let's start with getting an input. 

The tree portion of this input consists of two ```char``` '.' and '#'.

To save some memory, I am going to use ```bool``` data type '.' being 0 and '#' being 1.

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

Now we have to find the largest christmas tree, given the series of 0s and 1s.

Let's look at the Test Case

```
..#..
.###.
#####

or

00100
01110
11111
```

How would we find the largest tree in this scenario?

Let's assume that first 1 in first row is the largest tree, how many elements would this tree have?

It would have 9 elements with height of 3.

What about the first 1 in the second row?

It would have 4 elements wih height of 4.

If I make an array called ```int numberofgreenbyposition[100][100];``` with ```numberofgreenbyposition[i][j]=number of elements when (i,j) is the tip of the tree```

The result would look like

```
00900
04440
11111
```

To save more problems, we can use ```the number of element in tree = heightoftree^2```as well.

The comlexity of this solution of ```O(n^2)``` n= N*M = number of cells.

Click [Github]({{"https://github.com/Hanuu/google_kickstart_solution/blob/master/KickStart/2017RoundB/3.1.cpp"}}) to view the solution in Github. 

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
