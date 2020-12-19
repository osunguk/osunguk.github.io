---
layout: post
title: 코드 스테이츠 2주차
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

이에 대한 가장 직관적인 이미지가 있어서 가져와봤다. (Primitive 자료형에 symbol 도 있다.)

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

+추가 symbol 에 대해서 질문을 했더니 아직은 몰라도 된다고 하더라



<br>

## 화요일

1. typeof null 이 object 인 이유

개발자의 실수로 인해 if 문 하나가 빠져서 null 타입을 체크하는 구문이 빠졌다고 한다. 수정을 했지만 수정하면서 생기는 버그들이 많아서 수정을 포기했다고 한다... ㄸㄹㄹ...

그러면 어떻게 null 의 타입을 확인 해야 할까?

```javascript
let valueNull = null;
if(valueNull === null) // 이런식으로 타입을 찾아야 한다.
```

다시한번 레거시 코드가 얼마나 무서운지 깨닫는다...

<br>

2. 클로저 & 스코프

이에 대한 설명은 너무 길어져서 따로 주제로 선정해 포스팅을 하겠다

- [ ] 클로저 & 스코프 주제로 게시물 포스팅 하기

3. const 객체 의 값이 바뀌는 이유

```javascript
const obj = {};
const temp = obj; 
// 2번째 줄에서 temp에 들어가는 값는? => obj 객체의 주소값이 들어간다
// 따라서 const 로 보호되는 값은 obj 의 key,value 의 값이 아니라 주소값이 보호된다

const obj2 = {};
obj = obj2 // 이 구분을 실행하면 "Assignment to constant variable." 에러가 발생한다!
```

<br>

4. https://poiemaweb.com/ 여기 사이트 대다나다... 정독정독 하기!!

html, css, js, sass, bootstrap 등등... 방대한 자료를 아주 고급진 설명과 함께 게시되어 있다. JS 부분이 37세션으로 매우매우 디테일하게 설명 되어있는데 학습 진도와 같이 읽는다면 많은 도움이 될지 싶다!! (주말에 몰아봐야징..... ㅎ)

4. JS Symbol

- [ ] ~~주말에 하기~~ 아직 몰라도 된다하셨으니 나중에 배우면 블로깅 하기

## 수요일

1. Test code

- [ ] 주말에 하기

2. slice 메소드 정리!

```javascript
// 문법은 아래와 같다, 둘 다 동일하다.
arr.slice([begin[, end]])					// 배열의 경우
str.slice(beginIndex[, endIndex]) // 문자열의 경우

// **end 로 들어가는 인덱스 위치의 값은 추출되지 않는다!!!**

let a = [0,1,2,3,4,5,6,7,8,9,10];

a.slice(5) // [5, 6, 7, 8, 9, 10]
// 인수를 하나만 넘기면 slice(하나있는 전달인자, a의 마지막 index) 와 동일하게 작동함

a.slice(0,5) // [0, 1, 2, 3, 4]
// 처음부터 5번째 앞까지

a.slice(10000000000000) // []
// 범위를 넘어가면 깡통 반환

a.slice(0, 1000000) // [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
// 처음부터 끝까지 나온다

a.slice(7,3) // []
// if(first arg >= second arg) return []

a.slice(-6,8) //[5, 6, 7]
// 음수의 경우
// a.slice(a.length - 6, 8) 과 동일
```

<br>

3. 얕은 복사, 깊은 복사

얕은 복사와 깊은 복사가 각각 의미하는바를 요약해보자 

> 먼저 프로그래밍에서 '복사'는 뭘까?

```javascript
let a = 123;
let b = a;

b = b - 53;
console.log(a,b) // 123 70

let A = [123];
let B = A

A.push(1235);
console.log(A,B) // [123, 1235] [123, 1235]

// 위와 같은 현상을 피하기 위해서는 아래와 같이 새로운 주소를 가지는 배열로 만들어 줘야한다.
let C = []

for(let i=0; i<A.length; i++){
  C.push(A[i]);
}
// or
let D = A.slice(0);
```

a, b 는 값이 복사되어 완전히 분리된 값으로 계산된다 그러나 A, B 는 복사를 했는데 B의 동작에 A 가 영향을 받는다. 이는 배열은 값을 넘길 때 주소값을 넘기기 때문이다. 

이렇듯이 JS 에는 두가지값(value 와 reference)이 존재한다. 주소값은 해당 주소를 읽어 주소가 가리키는 값을 읽기에 하나의 깊이(depth)가 존재한다. 주소값을 읽지 않고 그대로 복사한다면 **얕은복사**, 주소를 가리키는 곳을 찾아가 해당하는 값을 찾아 복사하면 **깊은복사** 라고 보면 되겠다

이 주제에 대해 추천받은 [사이트](https://medium.com/watcha/%EA%B9%8A%EC%9D%80-%EB%B3%B5%EC%82%AC%EC%99%80-%EC%96%95%EC%9D%80-%EB%B3%B5%EC%82%AC%EC%97%90-%EB%8C%80%ED%95%9C-%EC%8B%AC%EB%8F%84%EC%9E%88%EB%8A%94-%EC%9D%B4%EC%95%BC%EA%B8%B0-2f7d797e008a)를 쭉 읽어보고 소감 정도만 적어도 필요한 부분을 얻을 수 있을 것같다. ~~절대 귀찮아서가 아니다~~

일단 공식적인 JS 에서는 깊은 복사를 지원하지 않는다. 해당 개발자는 '딥카피를 했을 때 code smell(좋지 않는 코드를 표현하는 말)이 났으며 사용하지 않았을 때 더 나은 솔루션을 얻을 수 있었다(개인적인 경험상)' 라고 말했다.

일부 라이브러리가 완벽한 깊은 복사를 구현했다. 하지만 깊은 복사를 사용하기 앞서 깊은 복사가 필요한지에 대한 고민을 먼저 해보는게 좋을 것 같다.

<br>

4. this 키워드

건드려서는 안되는걸 건드린거 같다

<br>

## 목요일

1. lexical 하다 Syntax and Sementics

눈으로 보이는대로 동작하다. 다르게 말하면 코드의 결과가 예측가능하다?

2. 콜스택? ~~아직은 깊이 몰라도 될 것같다.~~

기본적으로 함수가 호출할 때 stack 처럼 쌓이는 것을 말한다. (부른다 call + 쌓는다 stack 간단하쥬?)

<p align='center'><img src='https://i.imgur.com/fGQTi6q.png' alt='test' style='zoom:50%'/></p>

알아야하는 개념

- Event loop
- Callback queue
- Web Api

js 파일에서 함수가 실행되면 콜스택에 쌓이고 Web api 를 사용하거나 콜백함수라면? 콜백큐에 담겼다가 콜스택이 비워지면 이벤트 루프를 통해서 실행된다.

<br>

3. for(let ...) 고정고정

만약 반복문 안에서 var를 선언하면 for문이 끝나더라도 이 녀석이 죽지않고 살아서 우리를 끊임없이 괴롭힌다.

**포렛! 포렛!**

<br>

4. 클로저의 심화

name spacing 과 factory 패턴?

<br>

5. Notion 사용해보기

후기 공유회때 선배님이 노션와 블로그를 병행해서 기록을 효율적으로 남겼다해서 노션에 가입하고 사용해봤다. 이게 처음 마크다운을 접하고 문서 꾸몄을 때 느꼈던 희열을 다시 느꼈다. 여셩분들이 다꾸에 왜그렇게 목말라 하는지 알듯한? 느낌이 든다.

<br>

6. CSS 미디어 쿼리

@media 의 뜻을 이제야 알게 되었따!!

<br>

7. 부트스트랩 그리드 시스템

처음 화면을 설계할 때 화면 비율이나 크기를 구체적으로 잡을 수 있게 도와주는 시스템으로 보인다.

<br>

## 금요일

1. flex box frog

Flex 속성에 대해서 게임같이 플레이 하는 웹사이트가 있어서 해봤는데 너무 괜찮았다.

Flex-direction 속성이 column 일때 justify-content 와 align-items 의 적용도 바뀐다는 것만 적응을 잘하면 무리없이 사용할 수 있을 것 같다.

2. css	

사람들이 가지고 있는 기종마다 디스플레이 크기가 다르기 때문에 css  를 설계함에 있어서 크기에 따라 유연하게 작동하는 코드를 짜야하는데 굉장히 쉽지 않은 부분인거 같다.

어려운 부분

- float
- Flex 에서 비율로 나누는 것
- height:100% width:100% 에 대한 개념
- 왜 내가 생각한대로 보여주질 않는걸까? ~~(굉장히 lexical 하지 못하네)~~

<br>

## 주말

- 주중에 공부한 내용 정리 및 블로깅