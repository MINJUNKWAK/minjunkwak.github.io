---
layout: single
title: "좋은 서비스란 무엇일까"
date: 2018-05-04
categories: lettertosoldier
comments: true
author: MINJUN KWAK
lang: Korean
ref: blog
tags:
  - lettertosoldier
  - blog
---

좋은 서비스의 정의란 무엇일까?

작년에 lettertosoldier를 만들었을때 부터 생각을 했던 주제이다.

내가 처음 만들어본 서비스였고 생각보다 많은 사람들이 써주었기 때문도 있지만, 굉장히 controversial한 의견들을 많이 들었기도 하다.


아이디어 자체(군인들에게 바깥 소식을 전해준다)는 것은 굉장히 좋은 생각이다.

하지만 인터넷편지를 사용하는게 과연 맞는 접근이였을까?

많은 사람들이 우려를 한 부분이 두가지가 있었다.

1. 육군훈련소의 입장
2. 육군훈련소 기간병의 입장

첫번째로, 육군훈련소의 입장을 보았을때, 그다지 좋아하지 않을것이라는 생각이다.
대한민국 군대의 "군대식 일처리"를 생각해보았을때 이 서비스를 그닥 좋아할꺼 같지 않다는 결론은 쉽게 도달 할 수 있다. 

프로그램을 사용하면 몇번의 클릭으로 편지를 수백장까지 보낼 수 있기 때문에 훈련소의 입장에서는 잉크와 종이의 낭비로 생각을 할 수 있다. 

나는 훈련병의 알권리가 휠씬 더 중요하다고 생각 하지만,

<img src="/assets/images/goodservice/thearmyway.png">

군대식 일처리의 알고리즘을 적용한다면, 인터넷 편지를 아예 없에버리거나 편지 갯수에 제한을 두게 하는 등의 결론에 쉽게 도달한다.


두번째로, 육군훈련소 기간병의 입장을 생각을 보자. 이는 실제로 내가 개발을 하면서 하루에 수많은 테스트를 하면서 편지를 무지막지하게 보냈었는데, 거의 2천통은 보냈었다.

이때문에 매일 편지를 30장씩 잘라줬던 기간병이 곽민준 뭐하는 분이냐고 물어봤다고 전해 들었다.ㅋㅋ 다행이 친구가 기간병과의 관계가 좋아서 잘 넘어갔지만 고생하는 육군 장병에게 일을 더 주는 것 같아서 마음이 썩 편하지는 않았다.

공리주의의 관점에서 보았을때, 소대당 기간병 한명이 조금 더 고생하므로써, 그 소대 전체의 훈련병들이 더 나은 환경에서 훈련을 할 수 있다면 이득이라고 볼 수 있겠지만 이를 각 기간병들이 어떻게 받아 드릴지는 의문이다.



지난 2개월 정도 프로그램이 제대로 돌아가지 않았던 적이 있다.
어떤 문제인가 디버깅을 해보았을때 문제가 확연히 보였는데, 육군 훈련소 웹사이트의 편지를 보내는 구조를 바꿨기 때문에 생긴 오류였다.


빨리 고치고 싶었지만, 인턴 인터뷰들때문에 공부로 바뻤기 때문에 좀 걸렸는데 어제 결국 해결을 하였다. (다행히 인터뷰는 좋은 결과가 있었다. 조만간 정리해 올릴 예정)


웹사이트의 구조를 보았을때, 몇가지는 이 프로그램을 겨냥한듯한 업데이트가 몇가지 보였었다.

예를 들어 브라우저를 컨트롤할때 CSS selector를 찾아서 세부사항을 정하는데 selector의 이름이 몇가지 바꿔져있는 것을 확인 하였는데, 단순 변수명을 바꾸는 행위는 그저 이 프로그램을 겨냥한 것처럼 보였다.

또한, 편지를 보낸후에 다시 훈련병을 찾아야하는 구조로 바꿘것으로 봐서는(더 간단한 구조에서 복잡한 구조로) 유저의 편의를 위한 업데이트 보다는 다른 의도가 있었던것 같다.


이를 알아내었을때, 군대 특유의 비 합리성에 부딪힌것 같아서 마음이 아팠고 프로그램 업데이트를 중지해야하냐는 생각이 많이 들었었는데 얼마전에 읽은 댓글때문에 반드시 업데이트를 하겠다고 마음을 바꿨다.


<img src="/assets/images/goodservice/comment.png">


그래도 이 프로그램을 사용하므로써 즐거워 하는 사람이 있고, 훈련소의 부당함이 조금 줄어들고 훈련병의 알권리가 확보가 된다면, 나는 그것만으로 계속 이 프로그램을 업데이트 해나아가는 원동력을 확보를 한 것이라 생각을 한다.


좋은 서비스의 정의는 여러가지가 있다. 

내가 소프트웨어 개발자로써의 길을 걷게 된다면, 내가 서비스를 만들때 최선으로 생각을 할 것은, 내 자신도, 큰 기업도 아닌 사람(소비자)이다.

사용자가 만족을 하고 이것이 사회적으로 좋은 결과를 불러 일으킨다면, 그것이 좋은 서비스가 아닐까.


부디 앞으로의 여정에서 좋은 서비스들을 많이 만들었으면 좋겠다.