---
layout: post
title: var와 let과 const
categories: [javascript]
---

JS 에는 3가지 변수 선언 키워드가 있다.

var 는 레거시코드 ~~라떼코드~~ 를 이해하기 위해 설명한다 ( 사용하지말것!! )

|       | 스코프      | 호이스팅 | 재 할당 | 재 선언 |
| :---: | ----------- | -------- | ------- | ------- |
|  var  | 함수 스코프 | O        | O       | O       |
|  let  | 블럭 스코프 | X        | O       | X       |
| const | 블럭 스코프 | X        | X       | X       |

var 의 재선언 부분은 원래 error 가 나는게 정상인데 개발자 도구와 node 환경에서 실행한 결과 가능한걸로 보인다.

"use strict" 를 사용해도 동일한 결과 ~~잠수함 패치라도 했는감...~~

## var

ES5 까지 변수를 선언할 수 있는 유일한 방법이 var 를 사용하는 것이였다. 그러다보니 울며 겨자먹기 식으로 사용을 했고

ES6 에서 let, const 가 등장과 함께 var 을 퇴장 시켰어야 했으나 레거시 코드의 유지를 위해 남겨진 친구다.

var 키워드의 문제점을 보자!

```javascript
// 1. 함수 레벨 스코프
console.log(i); // undefined
{
  var i = 123;
}
console.log(i); // 123
// 블럭을 무시하는 스코프 ㅎㄷㄷ;;
// 선언 이전에 사용이 가능하다 (호이스팅 된다.)

// 2. 키워드 생략 가능
j = 'test';
console.log(j); // test

// 3. 중복선언 가능
var k = 213;
console.log(k); // 213
var k = 'what?';
console.log(k); // what?

```

결론 : 쓰지말자

<br>

## let, const

두 키워드의 차이는 **재 할당 여부** 하나 뿐이다. 그렇다면 재 할당 여부가 가지는 의미를 살펴보자

재 할당, 뭐를 다시 할당 한다는 것일까? 

**값?** 아니다 **주소다** 이 부분을 헷갈리면 배열과 객체의 데이터가 바뀜에도 const 가 왜 아무 반응을 하지 않는지 이해할 수 없다.

다음을 보자

```javascript
let x = 1;
let y = x;
x = x + 1;
console.log(y); // 1
```

콘솔로그에 찍히는 값은 `1`이 찍힌다. 코드를 라인별로 살펴보면

1번 라인 : 변수 x 를 선언 및 1 이라는 값을 할당

2번 라인 : 변수 y 를 선언 및 x 의 주소값을 할당

**3번 라인 : 변수 x 에 x 주소에 있는 값과 1을 더해서 재 할당 한다.**

위에서 언급한 것과 같이 3번 라인에서 x 에는 새로운 주소가 할당이 된다. 숫자 2의 값을 가리키는 새로운 주소가 x 에 담긴다.

y 는 기존에 x 로 부터 넘겨받은 1 을 가리키는 주소를 가지고 있으므로 console.log 에는 1 이 찍히게 된다.

**const** 키워드로 다시 한번 해보자

```javascript
const x = 1;
const y = x;
x = x + 1; // error 발생
```

1번 라인 : 변수 x 를 선언 및 1 이라는 값을 할당

2번 라인 : 변수 y 를 선언 및 x 의 주소값을 할당

3번 라인 : 변수 x 에 x 주소에 있는 값과 1을 더한 값을 가리키는 **새로운 주소를 할당**하려 하므로 error 를 발생

그럼 주소값을 가지는 Object 와 Array 의 경우를 살펴보자

```javascript
let obj1 = {};
const obj2 = {};

let arr1 = [];
const arr2 = [];

obj1.a = 'a';
obj2.a = 'a';

arr1.push('a');
arr2.push('a');

// 위의 코드는 error 없이 동작한다.
```

Object 와 Array 주소 값을 가지기 때문에 해당 주소안에서 변동되는 값에 대해선 error 를 생성하지 않는다.

그럼 let, const 로 객체와 배열을 선언하면 아무런 차이가 없는건가? 아니다!

마지막으로 예시를 보자

```javascript
let obj1 = {};
const obj2 = {};

let arr1 = [];
const arr2 = [];

obj1 = 123;
obj2 = []; // error 발생

arr1 = {}
arr2 = 'test' // error 발생
```

let 으로 선언한 변수는 새로운 주소가 들어와도 don't care

하지만 const 는 주소값을 변경하는 할당문을 사용하면 error 를 만든다.

<br>

## let과 const 은 언제 어떻게 써야할까?

이 부분은 순전히 개발자의 몫이다. 변수 자체가 개발자의 입장에서 어떻게 사용할 건지 결정하는 부분이기 때문에 절대적인 기준은 없다.

다만 값을 계속 변경하는 변수라면 let, 한번 받고 변경되지 않는다면 또는 변경되지 않아야 한다면 const 를 사용하는게 현명하다.