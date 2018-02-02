---
layout: single
title: "암호화폐와 한국의 인터넷 여론1"
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

2017년 한국에서 가장 핫했던 키워드 중에 하나는 "비트코인", 넓게 말하여 "암호화폐"였을 것이다. 

블록체인이라는 새로운 기술을 등에 지고 탄생한 새로운 화폐는 대한민국을 휩쓸었고 남녀노소 할것없이 다양한 사람들을 이 시장에 끌어 들였다.

하지만 아이러니하게도 이 화폐의 진정한 가치를 깨닫고 있는 사람을 많지는 않은것 같다.

<img src="/assets/images/koreancypto/naverblockchain.png">

위 그림은 네이버 데이터랩에서 가져온 자료로써 검색량의 변동성을 보여준다.

비트코인, 가상화폐, 그리고 블록체인 이 세 단어를 같이 비교해 보았을떄, 이 모든것의 중심이되는 블록체인의 검색량이 현저히 낮은 것을 확인 할 수 있다.

가상화폐(암호화폐, 나는 가상화폐라는 단어가 틀렸다고 생각하지만 현제 통용되는 단어이므로), 비트코인의 관심이 급상승했지만, 이를 설명할 기술을 이해하는 사람은 얼마나 될까.

그렇다면 사람들은 왜 암호화폐를 사고 파는 것일까?

<img src="/assets/images/koreancypto/gauza1.png">
<img src="/assets/images/koreancypto/gauza2.png">

호재가 있으면 상승하고, 악재가 있으면 하락하는 주식과 비교해 보았을때 암호화폐 가격의 변동성은 다른 방식으로 설명이 되어야한다.

많은 사람들은 암호화폐의 가능성을 보고 투자하기 보다는, 올랐으니까, 주변의 다른 사람들이 이걸로 돈을 버니까 시장에 투자를 했었고 

투자 전략또한 도박과 크게 다르지 않았다.

<img src="/assets/images/koreancypto/bluehouse.png">

사람이 사고, 사람이 파는 시장에서 행복한 꿈을 꾸었던 사람들은 결국 

<img src="/assets/images/koreancypto/seeyouinhell.png">

[분노하였고]({{"http://news.mt.co.kr/mtview.php?no=2018013114225924580"}})(총선은 2020년인데?)

<img src="/assets/images/koreancypto/seeyouinhell2.png">

시장은 참담하게 반응을 하였다.

이런 시장, 사람들이 가격을 형성하고 가격이 여론을 형성하며, 다시 여론이 가격을 형성하는 시장에서 여론을 분석하므로써 가격을 예측할수 있을까? 라는 물음에서 시작을 하여 

암호화폐의 가격을 텍스트 마이닝을 통하여 분석, 더 나아가 예측을 할 수 있을까?라는 생각을 해보게 되었다.

한국시장이 다른 나라들과 비교해서 프리미엄이 잡혀있다는 현상을 포함해서

한국의 암호화폐 시장과 한국의 여론의 관계를 찾을 수 있을까?

[비트코인과 구글트렌드, 위키피디아의 상관관계]({{"https://www.nature.com/articles/srep03415"}})를 다룬 사례도 있고

[게시판의 여론을 딥러닝을 통해여 비트코인 가격을 예측]({{"http://journals.plos.org/plosone/article?id=10.1371/journal.pone.0177630"}})한 사례도 존재하기 비교적 쉽게 수행 할 수 있을거라 생각을 했다.

우선 국내에서 가장 많은 글 리젠률과 조회수를 보유한 [디씨 인사이드 비트코인 갤러리]({{"http://gall.dcinside.com/board/lists/?id=bitcoins"}})의 데이터를 통하여 분석을 시도해 보자