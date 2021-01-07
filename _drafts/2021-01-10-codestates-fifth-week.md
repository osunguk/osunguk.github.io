---
layout: post
title: 코드 스테이츠 5주차
categories: [codestates]
---

코드 스테이츠를 통해 배운 것을 정리하는 post

> 무엇이든 보고 듣기는 쉽지만
> 자기 것으로 만드는 것엔 노력이 필요하다.

<br>

## 월요일

#### underbar _.zip 재귀로 풀기

이 문제를 풀기 위해 대략 4시간 정도를 투자한 것 같다. 애를 먹었던 부분이

일단 재귀함수가 손에 익숙하지 않은 상태였고, ...args 로 받아오는 배열을 처리하는 방법을 알지 못했다.

재귀는 while 문이랑 성격이 많이 비슷해서 while으로 먼저 해결을 하고 재귀로 변환 시켰고

...args 는 재귀를 부를때 ... (전개연산자) 를 사용해서 문제를 해결했다

<br>

#### 하노이 탑, 조합 재귀

하노이 탑의 점화식이 복잡하지 않아서 횟수를 구하는 것 어렵지 않았지만 해결하는 방법을 코드로 구현하니 약간 머리가 아파왔다.

정확히 어떤 근거와 이유에서 아래의 코드가 나왔는지는 모르겠지만

```javascript
function hanoi2(n, from, middle, to) {
  if (n === 1) console.log(`${n}을 ${from}에서 ${to}로 이동`);
  else {
    hanoi2(n - 1, from, to, middle);
    console.log(`${n}을 ${from}에서 ${to}로 이동`);
    hanoi2(n - 1, middle, from, to);
  }
}
```

어쨌든 동작한다! ㅋㅋ

<br>

조합 재귀는 뭔가 재밌었다. 뭔가 머릿속에서 재귀를 이용한 계산이 확확 돌아가서인지 코드의 흐름이 한번에 잡혀왔다.

```javascript
const getCombinations = function (arr, selectNumber) {
  const results = [];
  if (selectNumber === 1) return arr.map((value) => [value]); // 1개씩 택할 때, 바로 모든 배열의 원소 return

  arr.forEach((fixed, index, origin) => {
    const rest = origin.slice(index + 1); // 해당하는 fixed를 제외한 나머지 뒤
    const combinations = getCombinations(rest, selectNumber - 1); // 나머지에 대해서 조합을 구한다.
    const attached = combinations.map((combination) => [fixed, ...combination]); //  돌아온 조합에 떼 놓은(fixed) 값 붙이기
    results.push(...attached); // 배열 spread syntax 로 모두다 push
  });

  return results; // 결과 담긴 results return
}

let test = [1, 2, 3, 4];
console.log(getCombinations(test, 3));
```

arr 에서 하나씩 빼서 조합법?에 담은 다음에 나머지로 만들 수 있는 조합을 selectNumber가 1이 될때까지 재귀를 돌린다.

이렇게 하면 중복요소가 없는 모든 조합법이 다 나온다. 코드는 어디서 가져온거지만 흐름이 잘 보이고 함수들도 적재적소에 잘 쓰여진 느낌이 들어서 좋다.

참고로 순열은 반복이 허용되며 순서가 중요하다. 

<br>

#### 타이머 API

<code>setTimeout</code> 와 <code>setInterval</code>비동기 방식으로 동작하며 코드 흐름을 막지 않는다 (non blocking)

콜스택에서 바로 작업을 처리하라고 날라가며 작업을 완료하면 queue 에 완료된 순으로 들어간다

콜스택의 작업이 모두 끝나면 queue 들어온 순서대로 하나씩 꺼내서 처리한다.

<br>

- 내일 학습 내용

~~트위틀러 못한 작업 마무리 (로컬 저장소)~~

동기 & 비동기 이론 정리

~~underbar 어드밴드 다시보기~~

<br>

## 화요일

#### 날씨 API 사용해서 앱 만들기

뉴모피즘 기법을 적용했더니 엄청 그럴싸한 앱이 완성이 되었다 !!

<br>

#### Pre 코스 회고록 작성

이번 회고록은 글이 잘 안써져서 고생했는데, 다 쓰고 보니 얼마 안되서 좀 그랬지만 만족스러운 글이 나온 것 같다.

<br>

## 수요일

#### HA 코플릿 시험

기존 코플릿 문제들과 비교하면 난이도가 130% 정도 되는 것 같다.

예외처리에 대한 부담은 없지만 input 으로 들어오는 data 를 다루는데 손이 많이 갔다.

평소 알고리즘 푸는 걸 즐기던 터라 재밌게 풀었다!

<br>

#### underbar 새롭게 풀어보기

_.zip() 문제를 maxLength 를 사용하지 않는 방법을 찾다가 결국 재귀 방식으로 푸는 걸 도전!!

해당 문제를 새롭게 풀면서 재귀의 성격과 while 문과의 유사성 등등 많은 것을 느꼈다.

어드벤스를 다시 보면서 setTimeout 에 대해서도 복습 완료!

<br>

#### 트위틀러 로컬 스토리지 적용

매번 미루다가 이번에 적용했다.

새로운 트윗이 추가되면 로컬 스토리지에 저장되게 했다. 다만 조금 걸리는 부분이 새로고침을 하고 로컬 스토리지에서 데이터를 가져와서 화면에 뿌려주는데 <code>localStorage</code> 에 들어있는 데이터를 한번에 가져오는 메서드가 없어서 <code>for in</code> 으로 키 값을 가져와서 <code>length</code> 가 나오기 전까지 키 값을 이용했는데 이렇게 사용하는게 맞는지 잘 모르겠다.

그리고 key, value 형식으로 저장이 되는데 key 값을 뭔가 고유하게 줄만한걸 만들기 귀찮아서 모든 데이터를 배열에 담고 JSON.stringify 를 시켜서 담아 버리고 value 는 따로 넣지 않았다.

내 맘대로 쓰긴 했는데 아무튼 작동은 잘 된다.

sessonStorage 도 있었는데 local 은 영구저장 sesson 은 해당 세션, 창을 닫으면 날라간다.

<br>

- 내일 학습할 내용

~~트위틀러 시간 라이브러리 사용하기~~

~~JS dev 포스팅 1개 이상 작성하기~~

<br>

## 목요일

#### moment.js 라이브러리 사용

라이브러리는 가져오기까지 과정이 굉장히 험난했다. `npm install moment` 로 설치를 해서 `node_modules`에 있는 녀석을 쓰고싶었는데 

`Uncaught SyntaxError: Cannot use import statement outside a module` 이라는 오류때문에 발목이 잡혔다.

2시간 넘게 해결하려 아둥바둥하다가 [헬프 데스크](https://github.com/codestates/pre-help-desk/issues/2820)에 지원요청을 했다. 

+++추가

전에 같은 에러로 고생하신 분이 계서서 그 분의 [이슈](https://github.com/codestates/pre-help-desk/issues/2820) 를 통해 문제점이 뭔지 알게 되었다.

예상한 것같이 런타임 환경의 문제였고 이에 대해서는 IM 과정에서 `npm` 을 배우면서 자세히 배운다고 한다.

<br>

#### 트위틀러 좋아요 버튼 구현 & 로컬 스토리지 구현 방법에 대해서

urclass 에는 따로 언급이 없었지만 동기생분이 질문을 해주셔서 한번 구현을 해보았다. 

각각의 트윗에 좋아요 버튼과 수치를 표시하는 `span`을 달고 `div` 로 묶어 형제로 만들었다.

버튼 액션에서 타겟을 가져와 형제 span을 찾게 했고 수치를 조절할 수 있게 했다

<br>

**로컬 스토리지**

지금 내 트위틀러에 새로운 트윗이 생기면 로컬 스토리지에 새로운 key, value로 데이터가 들어간다. 다른 동기생분들께 로컬 스토리지를 어떻게 이용하셨는지 물어봤고 내가 사용한 방법이 굉장히 1차원적인 방법이라는걸 깨달았다.

`localStorage('tweetList', [트윗들의 정보들이 담긴 배열])` 식으로 했으면 굳이 번거롭게 `getItem` 을 힘들게 할 필요도 없었다.

지속가능한 개발의 환경이 갖춰지지 않은 내 트위틀러의 취약점이였다. 다시한번 설계의 중요성을 깨달았고 조금 더 신중해지자 되새겼다.

<br>

#### js 포스팅

1. `var`, `let`, `const` 에 대해서 포스팅을 했다. 기초적인 부분이지만 정확히 알고가야하는 부분이기 때문에 포스팅을 결정했다.
2. Scope 에 대해서 포스팅을 했다. 원래 클로저와 같이 하려 했으나 볼륨이 커져서 나눠서 포스팅 헷갈리는 부분이 있어서 쫙 정리도 할겸 포스팅을 결정했다.

<br>

#### jekyll 블로그 SEO 작업

내가 포스팅한 게시물들이 구글에 검색되면 좋겠다 하고 해서 찾아보고 **구글 서치 콘솔** 이란걸 찾아서 구글 봇이 내 블로그에서 글들을 가져갈 수 있도록 환경을 만들어 주는 작업을 했는데 생각보다 복잡하고 결과가 바로바로 나오는게 아니라서 진행이 되는지도 잘 모르겠지만 여러가지 작업들을 하면서 **검색** 이 어떻게 진행되는지 아주아주 조금은 알게되었다.

<br>

## 금요일



## 주말

