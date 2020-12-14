---
layout: post
title: 코드 스테이츠 주차

---

코드 스테이츠를 통해 배운 것을 정리하는 post

> 무엇이든 보고 듣기는 쉽지만
> 자기 것으로 만드는 것엔 노력이 필요하다.

<br>

## 월요일

1. NaN 만드는 비법 하나 추가요

Undefined 를 숫자와 연산을 시키면 => NaN 발생!

<br>

2. 배열 변수를 콘솔창에 출력할 때

console.log 가 아니라 console.table 을 쓰면 이쁘게 나오더라!!

2차원 배열도 표로 그려준다! (3차원은 3D라... )

![console.table()](https://i.imgur.com/rGHHwhC.png)

<br>

3. 브라우저 호환성

[이 사이트](https://gs.statcounter.com/)에 들어가면 전세계 or 어느 지역(나라)의 브라우저 점유율을 볼 수 있다. 아래는 우리나라 점유율이다. 

![korea-browser-share](https://i.imgur.com/QmZAsAW.png)

1위는 당당하게 크롬!!! 2위는 삼성 인터넷...? 이길래 찾아봤다. 그리고

모바일 플렛폼으로 갤럭시 폰의 모바일 인터넷이라는 알게되었다 (나는 아이폰유저라...) 근소한 차이로 사파리가 뒤를 따랏다.

이어서 호환성이 좋지 않은 IE 다른 나라들에 비해 점유율이 높다...!! (전세계 점유율은 엣지 브라우저 포함 4% 정도)

웨일 브라우저는 네이버에서 개발한 브라우저로 언제부턴가 네이버에 접속하면 위쪽에 광고 베너가 계속 뜨는걸 볼 수 있다.

Puffin 이라는 브라우저는 처음 봤고 Firefox 는 들어봤지만 우리나라에서 점유율이 매우 낮다.

<br>

위에서 보다시피 수많은 브라우저들이 사용되기 때문에 이에 개발도 맞춰서 개발해야하는 상황이다. IE 를 버릴 수 없는게 점유율이 결코 낮지 않고 한 때 한국 점유율 1등을 자랑하던 IE 였기에 그만큼 여기저기 스며들어있는 IE 가 있다. 

![IE-no-support](https://i.imgur.com/uFoCzE7.png)

만약 IE 까지 지원을 하는 프로젝트라면 호환성을 꼭 확인해야겠다.

<br>

3. Array method, immutable 과 mutable

- mutable 한 메서드들 - 원본을 바꾸는 함수들
  - push
  - pop
  - splice
  - shift
  - unshift
  - reverse
  - sort
- immutable 한 메서드들 - 원본은 그대로 둔채 계산된 결과를 return 한다.
  - concat
  - slice
  - filter
  - Map

<br>

3. Spread operator

반복 가능한 객체에 사용할 수 있으며 객체안에 있는 내용들을 펼쳐놓는? 작업을 한다

반복 가능한 객체의 종류는 대표적으로 **배열**과 **문자열**이 있다.

- 사용법

1) 함수(...반복가능한객체)

2) [...반복가능한객체, '3', 'str']

3) let temp = {...반복가능한객체}

아직은 안배웠지만 apply() 나 new 키워드를 사용할 때도 사용 가능하며 배열복사를 할 때도 가능하다!!

```javascript
let arr = [1,2,3];
let copyArr = [...arr]; // arr.slice() 와 같은 동작을 한다

function myFunction(x, y, z) { }
var args = [0, 1, 2];
myFunction(...args); // 이런식으로 args 를 전달할 때 간편하게 넘겨줄 수 있다.
```

<br>

3. [] === [] ? Primitive and reference

이에 대한 가장 직관적인 이미지가 있어서 가져와봤다.

![js-types](https://i.imgur.com/Pe3Snt1.png)

Object type 을 가지는 요소는 배열, 객체

즉, Primitive 는 실제 값을 가지고 Reference 는 실제 데이터를 가리키는 주소(위치) 값을 가진다.

그럼 아래 코드를 보자

```javascript
if ( [] === [] ) console.log('not work!');

// 배열은 주소값을 가지며 앞의 배열과 뒤의 배열의 주소는 다르기 때문에 조건문은 false 가 된다.
```

<br>

3. for ... in & for ... of

for ...in 은 모든 열거가 가능한 속성에 대해 반복을 하고

for ...of 는 컬렉션 전용으로 모든 객체가 아닌 [Symbol.iterator] 속성이 있는 모든 컬렉션 요소에 대해 반복을 진행한다.

무슨 말인지 이해가 안되서 여기저기 찾아본 결과! [여기](https://2dubbing.tistory.com/9) 괜찮은 설명이 있었다!!

아무래도 ES6 에서 추가된 Symbol 에 대한 이해가 더 필요해 보인다. ~~그래서 내일 하려구요...~~

아래의 뚜렷한 차이를 보이는 for ...in 과 for ...of 의 결과를 보면서 느낌만 알기!

```javascript
let iterable = [3, 5, 7];
iterable.foo = "hello";

for (let i in iterable) {
  console.log(i); // 결과 0, 1, 2, "foo"
}

for (let i of iterable) {
  console.log(i); // 결과 3, 5, 7
}
```

<br>

## 화요일



## 수요일



## 목요일



## 금요일



## 주말

