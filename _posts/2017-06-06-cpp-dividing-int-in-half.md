---
layout: single
title: "Cpp Dividing int in Half"
date: 2017-06-06
categories: algorithm
comments: true
author: MINJUN KWAK
lang: English
ref: dividinginhalf
tags:
  - cpp
  - algorithm
---

```cpp
#include<iostream>

using namespace std;

int main(){
    int a=10;
    int b=11;
    printf("(a+b)/2 = %d",(a+b)/2);
}

```
What would be the result of this code?

If the data types of 'a' and 'b' were double, the result would be 10.5.

However, the data types of 'a' and 'b' are int, will he result be 10? or 11?

Let's find out

```cpp
(a+b)/2 = 10
```

Between the two choices of rounding up and rounding down, the cpp have chosen to round down the number when number is the mean value of two.


```cpp
#include<iostream>

using namespace std;

int main(){
    int a=10;
    int b=11;
    printf("%d",(a+b)/4);
}

```

What about the caes when the number is below the mean value?

```cpp
(a+b)/2 = 5
```
Obviously, it rounds thenumber down as well.


```cpp
#include<iostream>

using namespace std;

int main(){
    int a=10;
    int b=11;
    printf("%d",(a+b)/8);
}
```
With the calculation being 2.625, will the result printed out as 3?

```cpp
(a+b)/2 = 2
```
Looks like cpp doesn't like the concept of rounding up.

```cpp
#include<iostream>

using namespace std;

int main(){
    int a=-10;
    int b=-11;
    printf("(a+b)/2 = %d\n",(a+b)/2);
    printf("(a+b)/4 = %d\n",(a+b)/4);
    printf("(a+b)/8 = %d\n",(a+b)/8);
}

```
What about the negative numbers? Will they round up the numbers? or round down?

```cpp
(a+b)/2 = -10
(a+b)/4 = -5
(a+b)/8 = -2
```

Surprisingly, the numbers were rounded up.

OR, May be they weren't rounding up nor rounding down the numbers, they were simply discarding decimals.

To be exact, let's look at the 'C++ International Stadard 2013', Section 4.9

<img src="/assets/images/dividinghalf.png">

Unlike my first assumption, it discards the decimals when converting float to int!