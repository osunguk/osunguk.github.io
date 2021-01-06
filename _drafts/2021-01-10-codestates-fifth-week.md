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

트위틀러 시간 라이브러리 사용하기

JS dev 포스팅 1개 이상 작성하기

<br>

## 목요일



## 금요일



## 주말

