---
layout: post
title: 코드 스테이츠 12주차
categories: [codestates]
---

코드 스테이츠를 통해 배운 것을 정리하는 post

> 무엇이든 보고 듣기는 쉽지만
> 자기 것으로 만드는 것엔 노력이 필요하다.

<br>

## 학습할 내용

- 

<br>

## 월요일

#### Redux

Cmarket 스프린트를 진행했다. 워낙 리덕스의 보일러플레이트가 진입장벽이 높다보니 모든 구성이 만들어져 있고, 빈칸을 채우듯 내용만 채우면 되는 스프린트여서 스스로 바닥에서 작성을 하라고하면 하지 못할 것 같다. 한번 꼭 스스로 코드를 작성해봐야겠다.

Component -> Dispatch -> Action -> Reducer -> Component 로 흘러가는 리덕스의 흐름을 잡을 수 있었던 스프린트였다. 뭔가 어려울 것  같은 첫인상과는 다르게 흐름을 타니 그래도 어떤 코드가 어떤 역할을 하는지 파악 할 수 있었다.

여러가지 미들웨어를 적용해보지는 못했지만 어디에 어떡해 적용하고 redux devtool 로 디버깅도 할 수 있다.

<br>

#### Hooks 연습

솔로 시간에 진행해야하는 줄 모르고 뒤늦게 페어분과 Hooks 를 사용했다. functional component 에서 state 를 가질 수 있는 방법으로 성능도 향상이되고 문법적으로도 간편하게 사용할 수 있기 때문에 사용하는걸 강력하게 추천한다. class component 의 모든 기능을 부족함 없이 구현할 수 있기 때문에 모든 코드를 functional component 로 작성해도 무방하다. Hooks 가 가지고있는 여러 메서드가 있는데 한번 정리를 해야겠다.

<br>

#### quick sort

저번에 작성했던 이진탐색트리의 pivot 느낌을 들고와서 적용해서 풀었다. 일반적인 데이터의 소팅 방법중 빠르다고해서 퀵소트의 이름이 붙었는데 pivot 을 어디껄 선택하느냐에 따라 속도를 비교하는 논문?을 본적도 있는 것 같다.

<br>

## 화요일

#### react-route-dom

리액트 SPA 앱에서 SEO 를 가능하게 할 수 있도록 도와주는 라이브러리이다. BrowserRouter, Switch, Route 를 사용해서 구현을 하는데 내부적으로는 SPA 처럼 동작하지만 URL 은 각각의 페이지마다 변경할 수 있다. 

<br>

#### hooks

useState 와 useEffect 를 직접 사용해 봤다. 확실히 class 형 컴포넌트에서 사용하는 코드보다 라인수가 현저히 줄어들고 직관적인 코딩이 가능했다.

<br>

## 수요일

#### DB 개요

DB 를 사용하기위한 사전 작업을 했다. 학부 시절에 배웠던 DB 내용들이 기억이나 엄청 반가웠던 시간이였다. 여러가지 세팅을 하고 예전에 쓰던 mysql workbench도 만났지만... DBeaver 가 UI 나 여러 방면에서 라이트하게 사용하기 좋았던것 같다. Sequel Pro 도 선택지에 있었는데 계속해서 에러를 뱉는 바람에 ~~삭제~~

<br>

## 목요일

#### Learn SQL

전반적인 쿼리문들 다루는 기술들을 익혔다. JOIN 문을 작성해는 부분은 뭔가 새로워서 디테일하게 공부를 했다.

<br>

#### Cmarket DB

connection 하는 부분이나 세팅 관련부분이 전부 구비?가 되어있어서 추후에 꼭 세팅하는 법까지 학습을 할 필요가 있어 보였다. 기존에 만들었던 redux prj 에 db 부분을 융합했는데, 액션에 따라 DB 에서 데이터를 불러오거나 저장하는 작업을 진행했다.  전부해서 40줄도 안되는 작업인데 생각보다 고된 시간이였다.

<br>

## 금요일

#### 리덕스에서 미들웨어가 적용되는 원리

리덕스에 `applyMiddleware` 라는 메서드가 있고 인자로 미들웨어들을 받는다. 

> [Middleware](https://redux.js.org/understanding/thinking-in-redux/glossary#middleware) wraps the base dispatch function. It allows the dispatch function to handle [async actions](https://redux.js.org/understanding/thinking-in-redux/glossary#async-action) in addition to actions. Middleware may transform, delay, ignore, or otherwise interpret actions or async actions before passing them to the next middleware. See below for more information.

리덕스 공식 문서에 나와있는 내용이며, 조금 살펴보면 "미들웨어는 작업 또는 비동기 작업을 다음 미들웨어에 전달하기 전에 변환, 지연, 무시 또는 다른 방식으로 해석할 수 있습니다." 라고 적혀있으며 해당 액션에 대해 전처리? 작업을 해줄 수 있다.

<br>

#### redux-thunk

```javascript
function createThunkMiddleware(extraArgument) {
  return ({ dispatch, getState }) => (next) => (action) => {
    if (typeof action === 'function') {
      return action(dispatch, getState, extraArgument);
    }

    return next(action);
  };
}

const thunk = createThunkMiddleware();
thunk.withExtraArgument = createThunkMiddleware;

export default thunk;
```

위에 보이는 코드가 redux-thunk 코드 전부이다. 액션이 들어왔을 때 액션의 타입이 함수라면 인자로 dispatch, getState, extraArgument 를 넘겨줘서 액션함수 안에서 또 다시 액션을 발생시킬 수 있다.

<br>

#### Cmarket-DB 레퍼런스 코드 및 디렉토리 구조 분석

해당 프로젝트가 MVC 패턴에 알맞게 구성이 되어있다고 엔지니어 분께서 얘길 해주셔서 각각의 디렉토리와 파일들이 가지는 의미와 동작들을 분석했다. 전부 다 하진 못했고 주말중에 해부를 마저 해야될 것 같다.

<br>

## 주말

#### Cmarket-DB 레퍼런스 코드 및 디렉토리 구조 분석 마무리

디렉토리와 파일 구조를 계속 보다보니 어느정도 패턴이 눈에 익기 시작했다. 이제는 직접 만들어보면서 체화를 시키는 단계가 필요하다.

<br>

#### React 공식문서 공부

어느정도 리액트에 대해서 안다고 생각을 했는데 공식문서를 다시 공부하면서 이 부분이 이걸 말하는 거였구나 라던가 처음 봤을 때 눈에 띄지 않던 부분들이 보였다. 특히 컴포넌트는 불변객체라고 언급 된 부분, setState 가 왜 비동기로 동작되어야 하는가? 같은 내용을 다시한번 굳게 다지는 시간이 되었다.

<br>

#### Redux 공식문서 공부

이번에 공부를 하면서 리덕스 공식문서를 처음 접했는데, 공식문서도 이쁘게 꾸며져있고 각각의 개념에 대한 설명들이 잘 나와있는것 같아서 다음 공부시간에 중점적으로 학습을 해볼 생각이다.

