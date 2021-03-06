---
layout: post
title: 코드 스테이츠 11주차
categories: [codestates]
---

코드 스테이츠를 통해 배운 것을 정리하는 post

> 무엇이든 보고 듣기는 쉽지만
> 자기 것으로 만드는 것엔 노력이 필요하다.

<br>

## 학습할 내용

- 스토리북
- ~~SSR CSR~~

<br>

## 월요일

#### Recast.ly

점점 실제 웹에 존재하는 페이지의 동작처럼 기능을 만들어가고 있다. React 를 사용하는 것도 조금씩 익숙해지기 시작해서 state, props 를 사용하는 것이나 구조분해할당을 이용한 데이터 할당도 적용했다. 스토리북이라는 라이브러리? 컴포넌트가 실제로 어떻게 화면에 표시되는지 확인할 수 있는 혜자스런 기능인데 사용법을 아직 몰라서 공부를 꼭 해봐야 겠다.

<br>

## 화요일

#### 클론 코딩

Recast.ly 스프린트가 예상보다 빨리 끝나서 페어분과 사이트 하나를 클론 코딩 해보자해서 [와디즈](https://www.wadiz.kr/web/wreward/main?keyword=&endYn=ALL&order=recommend)의 펀딩하기 페이지를 클론을 해봤다. React 를 이용해서 화면을 만들다보니 예전에 트위틀러를 만들 때보다 JSX 같은 기술을 쓰다보니 장점이 두드러지게 나타났다. 컴포넌트를 재사용 가능하게 만들 수 있고 상태를 가질 수 있어 만약에 ajax의 기능이 생긴다면 받아온 데이터를 담을 공간도 관리가 수월하다는걸 느꼈다.

HTML과 CSS 에 대한 깊이가 많이 부족하다는걸 많이 느낀 시간이기도 했다. 

<br>

## 수요일

#### Youtube API

유튜브에서 api 를 받아와서 검색어에 대한 유튜브 영상 데이터를 받아오고 받아온 데이터를 화면에 뿌려주는 굉장히 그럴싸한 페이지가 만들어 졌다. 지금까지 스프린트를 진행하면서 배웠던 것을 종합적으로 사용해서 만드는 느낌이 들어서 프로젝트를 하면 이런 느낌일까? 라는 생각도 들었다.

<br>

## 목요일

#### HA 대비

HA 에서 영화 관련 과제가 나온다길래 영화 api 를 이용해서 화면에 뿌려주고, 타이틀을 누르면 상세 정보가 나오는 작업을 해봤다. `create-react-app` 으로 맨땅에서 만들어 나갔는데 재밌었다. 서버도 express 를 정말 오랜만에 만났는데 자주 들러서 얘기도 하고 해야겠다.

<br>

## 금요일

#### HA

전날 복습했던 내용과 유사하게 나와서? 큰 막힘 없이 잘 풀어나갔다. 저번에도 그랬었는데 테스트 코드의 구조를 따라가야하는 강제성이 조금 아쉬웠다.  서버와 클라이언트 두개를 모두 구현했는데 연결해서 작동하게하는 테스트 코드가 없어서 이 부분도 아쉬웠다. 

전반적으로 리액트는 배울수록 재밌는 친구인듯하다. 짝사랑으로 시작해서 슬슬 넘어와주는 느낌이랄까... 

<br>

#### 후기 공유회

[Retrievo](https://retrievo.io/) 프로젝트의 구성원 중에 한분으로 엄청난 퀄리티의 결과물로 많은 사람을 놀라게하셨던 분이였다. 그런 분의 후기 공유회를 들을 수 있는 좋은 기회여서 참석해서 듣게 되었는데, 다 듣고난 소감은 '세상에 이렇게 긍정적이고 도전적인 사람도 있구나' 였다. **Just Do It !!** 를 모토삼아 할 수 없다는 핑계를 대기전에 부딪혀보시는 듯 했다. 삽질에 대해서도 얘길 해주셨는데, 클론 코딩도 그리 좋지 않다고 말씀하실 정도로 직접 몸소 체험하는 경험을 중요시 하시는듯 했다. 질문으로 "삽질은 커리큘럼따라 공부하는 것보다 시간이 상당히 소요되는데 코드 스테이츠를 수강하면서 그런 여유가 있으셨나요?" 라는 질문에 "삽질은 시간이 있어서 하는 것이 아니다." 라는 지혜로운 답변 ~~우문현답~~ 을 주셔서 뒷통수를 한대 맞은것 마냥 머리가 울렸다. 그 외에도 공부에 담긴 철학이 남다르셨다. 배우는걸 진정으로 즐기시는 것 같았고, 탐구심도 남다르셔서 비단 프로그래밍뿐만 아니라 무엇을 배우시든 잘 배우실 거라는 생각이 들었다. 공부의 목적에 대해서 다시 돌아보게되는 귀중한 시간이였다.

## 주말

#### TIL

게속해서 TIL 작성을 미루다가 오늘(토요일...)에서야 일주일치 TIL 을 정리하고 있다. 일주일 동안 무엇을 공부했는지 돌아보는 시간도 되었지만 그래도 당일 배운건 당일날 정리해서 올리는게 기억에도 많이 남고 적을 것도 많이 적는 것 같다. 

<br>

#### 알프레드

알프레드에게 쓰지 않는 기능들을 제거하고 필요했던 기능 ( 한 -> 영 변환 , 영 -> 한 변환, 유튜브 검색 등등...) url 에다가 적는 걸 이용해서 해당 주소의 검색어로 바로 들어갈 수 있게 해준다. 

원래라면

- 해당 페이지로 이동
- 페이지의 검색창에다가 검색
- 결과확인

이 루틴이

- 알프레드 키워드로 검색어 입력
- 결과확인

이렇게 변한다. 계속 수정해야지 생각만하다가 이번에 수정을 했는데 생각보다 너무 간편하다. good...

<br>

#### 서버 사이드 랜더링, 클라이언트 사이드 렌더링

최종적으로 화면에 보여지는 화면이 어디서 만들어 지느냐에 따라 서버 사이드. 클라이언트 사이드로 나뉘게 된다. 각각의 렌더링 방법의 장점들을 모아 만든 라이브러리가 Next.js

<br>

#### react-route-dom

리액트에서 CSR 를 구현할 수 있도록 도와주는 라이브러리다. 사용법도 간편하고 직관적이여서 손쉽게 구현시킬 수 있다.

<br>

#### img vs background-image

이미지를 표현하는 대표적인 두가지 방법 `background-image` 은 옛날 방법이며 여러가지 측면에서 불리한 부분이 많기 때문에 `<picture>` 와 같이 `<img>` 를 쓰는게 좋을 것 같다

<br>

#### Google 메인 페이지 클론 코딩

매번 클론 코딩을 진행할 때마다 뭔가 새롭게 배운다는게 너무 신기하다. 이번 작업을 하면서 배운것

- flex 속성 값의 의미

평소에 사용할 때 정렬할 때만 사용해서 자식요소의 속성인 flex 에 대해서 잘 몰랐는데 이번 기회에 정확하게 개념을 잡았다.

`flex: 1 1 auto` 

앞의 1은 부모 엘리먼트의 크기가 커질때에 따른 성장비율 0 이라면 크기에 따라 커지지 않는다

뒤의 1은 부모 엘리먼트의 크기가 작아질때에 따른 성장비율 0 이라면 크기에 따라 작아지지 않는다.

마지막 요소는 아직 정확하게 auto 와 0 의 차이는 헷갈리지만 (절대적 크기와 콘텐츠 크기의 차이라고 한다...) 기본 default 크기를 설정해 주는 속성이다.

- Input 창 안에 있는 것처럼 보이는 이미지 요소들

알고보니 인풋창 안에 있던게 아니고 div 를 인풋창처럼 꾸민거였다.... 약간 배신감이 느껴졌었다... ㅠ

- flex 설정시 margin: auto

를 하면 부모요소의 중앙 정렬을 하게 된다 (코드를 줄일 수 있다!!)

- `<picture>` `<img>` 사용

처음 적용을 해봤는데 이미지에 대해서는 조금 더 탐구를 해봐야겠다.

- Sass 적용해보기

Css 를 사용할 때 매번 불편했던게 부모 엘리먼트와 자식 엘리먼트를 적용하는 코드가 가시적으로 보이지 않아서 불편했는데 이런 부분을 계단식으로 지원해주는 Sass 를 사용해서 조금 더 나은 생산성을 기대해볼 수 있다.

<br>

#### 리덕스 맛보기

리덕스를 왜 사용하고 mobX 와는 어떻게 다른지 아주 살짝 맛만 봤다. 리덕스를 만드신 분이 어떤 분인지는 모르겠지만 정말 잘만드신 것 같다는 생각이 들었다. 컴포넌트에서 상태관리에 대한 부분을 분리해서 관리할 수 있도록 패러다임을 바꾼 라이브러리 같다. 

리액트를 쓰면서 유지보수가 힘들었던 props drilling 문제를 해결할 수 있어서 어서 배워서 써먹어 보고 싶다.

<br>