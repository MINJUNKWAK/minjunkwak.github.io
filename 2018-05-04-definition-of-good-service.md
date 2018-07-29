---
layout: single
<<<<<<< HEAD
title: "Definition of a good service"
date: 2018-05-13
categories: lettertosoldier
comments: true
author: MINJUN KWAK
lang: Korean
=======
title: "Definition of a Good Service"
date: 2018-05-04
categories: lettertosoldier
comments: true
author: MINJUN KWAK
lang: English
>>>>>>> 103dee45e20d46131447c2d01129050fc641e7fd
ref: blog
tags:
  - lettertosoldier
  - blog
---

What would be the definition of a good service?

<<<<<<< HEAD
It's a question that I've been thinging for the last few months, since I've deployed "lettertosolider"

Part of it was because it was my first deployable project, but part of it was because it was a controversial project.

The idea, which was to send the outside news to soldiers, was a great idea.

However, implementing it using the internet letter system that the Army has? Would it be a good idea?

Many people gave their concerns, mostly in two ways.

1. The ROK Army Training center
2. The soldiers in ROK Army Training center


Firstly, when we take a look at the ROK Army Training Center, we can easily come to a conclusion that they won't be supporting this porgram.



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
=======
It is a question that has been stuck in my mind since I've been making the [lettertosoldier]("https://minjunkwak.github.io/lettertosoldier/lettertosoldier-download/").

It was my first deployalbe project and at the same time, and there were real users. At the same time, there were lots of controversial opinions.

The idea, which was to send outside news to soldiers, was a great idea.

However, could the result justify the mean?

Was using "internet letter system in ROK Army" the correct approach?

Many people gave me concerns from varies areas, mostly two:

1. ROKA Training Center's perspective
2. Soldiers(Instructors) in ROKA Training Center

Firstly, taking into the ROKA Training Center's perspective, they wouldn't be supporting the program.
Just like average army in this country, the ROKATC is not the most reasonable orgnazation.

This program, or application, can send hundreds of letters with just few clicks. Which would lead to more spending on inks and papers.

I believe in freedom of journalism. And I think it was unfair for soldiers who are sacrifing their lives are blocked from freedom of information.

I believed this then, when I was in the ROKA training center, and I still believe it now.

However,I could foresee that, this could result in termination of "internet letter system" or at least slight modification to complicate the proces

Secondly, let's think about the soldiers who are duty station is ROKA Training Center.

In the process of developing this program, I had to test for the new features and bugs every time I encounter them.

I mainly sent this to one of my closest friend who was a trainee at that time.

I think I almost sent 2,000 letters.

Later, I heard that the soldier who was responsible for handing out the letter, had to do extra work to printing and cutting the letters that I sent.

After hearing this, I felt bad, beacuse I thought I was giving him the burden.

In the perspective of utilitarianism, if we sacrifice one man in each company about 10 minutes a day, which would yield one company of trainees for a better environment, it would be a success.


For last two months, the program was not functioning right. While solving the issue, I notice there was a slight change in the website structure.

I was eager to solver the issue, but I was so busy preparing for the intern interviews. (Luckly I got an offer from Google)

And I solved the issue yesterday, it seemed like the structual modification was caused by this program.

For example, there were some changes in variable names in CSS selectors. The program finds designated CSS selector to control the browser. It seems like a meaningless modification.

Also, they added an unadditional procedure when sending an letter. (which was totally meaningless as well, why would they change to process to more time-consuming and complex from simple and quick)

When I discovered the modifications, part of me thought, "may be I should stop deploying this program". This was a free distribution with zero profit and ROKATC discouraged me.

However, a comment from a stranger gave me strength to continue.

<img src="/assets/images/goodservice/comment.png">
(I am having same error message from the guys below..
When are you planning to fix this issue? I am so sorry to bother you because This is a free distribution and I am not at the position to demand anything. It is just that I join next week, and this really is a useful program... Thank you)

There are people who become happy by using this program. And unfairness of ROKATC could be solved. I guess that is the motivation behind why I should contine deploying this project.

There are numerous definitions of a good service.

If I am starting my career as a software engineer. The first think I should think about making a service is users. It is not myself, nor the big companies or organizations.

If users staify and it supports the social benefit, I believe that is a good service

I hope I would be developing lots of good service thoughout my career.
>>>>>>> 103dee45e20d46131447c2d01129050fc641e7fd
