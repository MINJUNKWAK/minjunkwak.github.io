---
layout: single
title: "암호화폐와 한국 인터넷 여론2"
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

# 해외시장, 논문다시 읽기
일단 앞서 [전 게시글]({{"https://minjunkwak.github.io/cryptocurrency/analyzing-cyptocurrency-based-on-korean-web1-kor/"}})을 참고하여 비교할 만한 지표를 만들어내자.

<img src="/assets/images/koreancypto/googletrendvsbtc.png">

구간은 2017년 6월 5일 부터 2018년 1월 24일까지로 잡았다.(짧은 구간이지만, 뒤에서 비교를 하게되는 한국거래소의 가격을 저정도 밖에 구할수 밖에 없었다.)

구글 트렌드를 통해서 본 "비트코인" 하루단위 검색량의 변동과 bitifinex의 비트코인의 가격(하루단위 시작가)의 그래프이다.

어느 정도 상관관계가 있는것으로 파악이되는데 Correlation Coefficient를 계산을 하면 0.838806이 나온다.

위와같은 일정 경향성(trend)이 있는 경우는 통계적 오류를 피해기 위해서 두변수에 log를 씌워서 Correlation을 구하게 되는데 이경우는 Correlation이 0.921012로 나오게 된다.

참고를 하였던 논문의 경우 2011년 5월 1일 ~ 2013년 6월 30일까지의 구글트렌드 데이터(주간)를 분석을 한 결과

log스케일의 correlation이 0.8786으로 나타났다.


이를 바탕으로 이야기를 하자면: 
- 비트코인에 한하여 구글의 검색량과 가격은 정비례 관계를 가진다
- 어느정도의 경향성을 줄이기 위하여 취한 log스케일의 경우 더 높은 관계를 보인다.
- 구글 검색량을 사람들의 관심도를 알려주는 지표로 생각을 한다면
- 비트코인에 대한 사람들의 관심과 비트코인의 가격이 정비례 관계에 있다

정도로 추론를 해 볼 수 있다. 

# 한국시장, 네이버
이제 한국시장에 국한을 하여서 데이터를 다시 얻어 보자

최근 몇 달간 네이버에서 실시간 급상승 검색어에 비트코인이 올라오는 것을 심심치 않게 볼 수 있었는데 이를 바탕으로 비교를 해보자

<img src="/assets/images/koreancypto/naverdatalabvsbtc.png">

구글 트렌드와 비교를 했을때 유난히 값들이 많이 튀는 현상을 볼 수 있다.

전세계사람들이 쓰는 구글 검색 엔진과 국내에 특화되어있는 네이버 엔진의 차이점이라고 볼 수 있겠다.

이를 바탕으로 Corrlation을 구하면: 0.589729

이 역시 경향성을 없애주기 위하여 log scae을 이용하면:0.556100

이 나온다.

구글 트렌드와 비교를 하였을때 상관관계가 확연히 달라짐을 볼 수 있다.

# 한국시장, 비트코인 갤러리
일단 비트코인 갤러리에 존재하는 글들을 모아보자

<img src="/assets/images/koreancypto/galldata1.png">

비트코인 갤러리에 존재하는 모든글 (2013.11.11 ~ 현재시점)까지 모아서 

한국 거래소인 빗썸의 가격(2017.06.05 ~ 현재)까지와 비교분석을 실시하면 된다.

일단 첫번째로 단순 게시글 수 비교를 해보자

<img src="/assets/images/koreancypto/numberofarticlevsbtc.png">

한국 거래소의 가격을 2017.06.05부터 구했기 때문에 비트코인 갤러리 역시 같은 구간을 갖고 있어야 한다.

두 변수 간의 Correlation은 0.929168
두 변수에 log를 씌워줬을 경우는 0.902580이 나온다.

생각 보다 높은 상관계수를 갖고 있음을 깨달을 수 있는데

이를 바탕으로 처음에 생각했던 비트코인 가격과 인터넷의 관심도가 비례한다는 가설을 뒷받침한다.

위의 상관계수들을 표로 정리하면


|  | google trend | naver data lab | bitcoin gallery |
|-------|-------|--------|---------|---------|
| Correlation | 0.921012 | 0.589729 | 0.929168 |
| Correlation with log | 0.8786 | 0.556100 | 0.902580 |


이렇게 된다.

[다음글]({{"https://minjunkwak.github.io/cryptocurrency/analyzing-cyptocurrency-based-on-korean-web3-kor/"}})에서는 비트코인 갤러리에 특정 단어의 언급횟수와 가격의 상관관계를 다룰 예정이다.


















