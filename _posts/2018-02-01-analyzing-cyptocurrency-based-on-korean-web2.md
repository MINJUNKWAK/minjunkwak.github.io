---
layout: single
title: "Crypto Currency and Korean Web2"
date: 2018-02-01
categories: cryptocurrency
comments: true
author: MINJUN KWAK
lang: Korean
ref: koreancrypto1
tags:
  - cryptocurrency
  - 암호화폐
  - Bitcoin
  - 비트코인
  - Analytic
  - 통계
  - textmining
  - 텍스트마이닝
---

# Foreign Market, Reading the papers again
Based on the [previous post]({{"https://minjunkwak.github.io/cryptocurrency/analyzing-cyptocurrency-based-on-korean-web1-kor/"}}), I should make a compariable reference.

<img src="/assets/images/koreancypto/googletrendvsbtc.png">

The range is between 2017 June 5th ~ 2018 January 24th.(Due to the limited data provided by Korean exchange websites)

The graph above shows daily start price of bitcoin (data proved by bitifinex) and daily google search querry data.

If we calculate the correlation coefficient, the result is 0.838806.

If datas have "trends" over timeline, the log scale is applied to variables. The correlation coefficient of two variables under the log scale is 0.921012.

The study that I used as a reference showed the correlation coefficient of 0.8786, when comparing between weekly google trend data and price over the range of May 1 2011 and June 30 2013.

Based on the result:
- The price of bitcoin and google search querries are directly proportional to each other
- When log scale is used to variables, it shows higher relationship
- If we consider the google search querry as "general public's interest"
- The price of bitcoin and general public's interest are directly proportional to each other

# Korean Market, Naver

It's time to focus solely on Korean maket.

Over the few months, the word "bitcoin" appeared several times in real-time search rank in Naver (the biggest portal site in Korea).

<img src="/assets/images/koreancypto/naverdatalabvsbtc.png">

Compare to the graph above, the inconsistency of search querry is shown.

Based on the data, the correlation coefficient is: 0.589729

The correlation coefficient of log scaled data is: 0.556100

The clear difference is shown.

# Korean Market, Bitcoin Gallery

Let's collect all the articles in bitcoin gallery.

<img src="/assets/images/koreancypto/galldata1.png">

Starting from November 11 2013 to current date, I've gathered all the articles in bitcoin gallery.

Now let's compare with the price of bitcoin provided by Bithumb, the biggest crypto currency exchange website. (Sadly the oldest data the could be achieved was from June 5 2017)

First, let's compare number of article and price of bitcoin

<img src="/assets/images/koreancypto/numberofarticlevsbtc.png">

Starting from June 5 2017,

The correlation coefficient is 0.929168
The correlation coefficient using log scale is 0.902580

It has more relationship than I expected.

It supports the theory of "bitcoin price and overall interest in internet is directly proportional to each other".

Making those correlation coefficient as table,

|  | google trend | naver data lab | bitcoin gallery |
|-------|-------|--------|---------|---------|
| Correlation | 0.921012 | 0.589729 | 0.929168 |
| Correlation with log | 0.8786 | 0.556100 | 0.902580 |


[The next article]({{"https://minjunkwak.github.io/cryptocurrency/analyzing-cyptocurrency-based-on-korean-web3-kor/"}} will be about the relationship between curtain keywords appearing in bitcoin gallery and the price .


















