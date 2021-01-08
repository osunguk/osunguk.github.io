---
layout: post
title: 자바스크립트 클로저
categories: [javascript]
---

## 클로저는 왜쓸까?

- 내부 변수를 private 하게 만들어 주기 위해서
- 프로그램이 커지거나 다루는 데이터가 많아지면 사용하는 변수에 대한 접근을 함수를 통해 안전하게 접근할 필요가 있다
- 커링 기술과 함께 파라미터를 유연하게 받기 위한 기술로써 쓰인다.
- 고차함수 메서드에서 펙토리 패턴처럼 사용할 수 있다.

<br>

### MDN 에서는 클로저를 다음과 같이 정의한다.

> 함수와 함수가 선언된 어휘적 환경의 조합이다.

처음 봤을 때 도통 무슨말을 하는지 이해가 가지 않았다. 코드를 먼저 살펴보자

```javascript
function foo(){ // 외부 함수
  let text = 'hello';
	return function boo(){ // 내부 함수
    console.log(text);
    return text;
  }
}
```

우리가 봐야하는 함수는 `boo()` 즉, 내부 함수이다.

아까 위에 적었던 맨트를 다시 떠올려보면 *함수와 함수가 선언된 ...* 여기서 **함수**는 `boo()` 함수를 말하는 것이고 **함수가 선언된** 은 함수가 선언된 위치를 보면된다. [저번 포스트](https://osunguk.github.io/javascript/2021/01/08/js-scope/) 를 기억하며 함수가 선언된 위치의 스코프를 살펴보자

`boo()` 의 스코프는 `foo()` 함수의 블럭이라는걸 알 수 있다.

그렇다면 함수와 함수가 선언된 어휘적 환경이 무엇인지 알았으니 **조합** 의 뜻만 명확하게 하면 끝난다. 찾아봤으나 조합은 **기억한다** 정도로 이해하면 될 것 같다.

<br>

### 내부 변수를 private 하게

```javascript
function book(title) {
  return {
    get_title: function (){
      return title;
    },
    set_title: function(_title) {
      if (typeof _title === 'string') {
        title = _title;
      }
    }
  }
}

coding = book('coding');
console.log(coding.get_title()); // coding
coding.set_title(123);
console.log(coding.get_title()); // coding
coding.set_title('Code');
console.log(coding.get_title()); // Code
```

`book()` 안에 있는 title 이라는 변수는 외부에서 참조할 수 없고 내장 메서드를 이용해야만 변수에 참조가 가능하다.

이는 **변수가 원치 않은 코드로 부터 변경되는 것을 방지**할 수 있다. 

저렇게 title 과 같이 사용되는 변수를 **자유변수**라고 말한다.

<br>

### 커링를 사용한다면

먼저 커링에 대해 간단하게 설명을 하자면

> 커링은 다수의 인자를 유연하게 받아오기 위한 기법의 일종

인자를 입력하는 타이밍이 각자 다르고 확실하지 않을 때 사용할 수 있다.

```javascript
function curring(x, y, z) { // 커링을 잘 못 사용한 예
  return function inner() {
    return `first argt : ${x} second argt : ${y} third argt : ${z}`;
  }
}

const oneArgs = curring(1);
console.log(oneArmt());

const twoArgs = curring(1, 2);
console.log(twoArmt());

const threeArgs = curring(1, 2, 3);
console.log(threeArmt());

// 인자를 유연하게 받아 올 수 없다.
// 각각의 파라미터를 자유변수로 만들고 기억하게 한다면 더욱 유연하게 인자를 받을 수 있다.

function curring2(x) { // 커링을 잘 사용한 예
  return function inner(y) {
    return function ininner(z) {
      return `first argt : ${x} second argt : ${y} third argt : ${z}`;
    }
  }
}

const oneArmt2 = curring2(1);
console.log(oneArmt2(2)(3));

const twoArmt2 = curring2(1)(2);
console.log(twoArmt2(3));

const threeArmt2 = curring2(1)(2)(3);
console.log(threeArmt2);

// 함수를 사용하는 모양새가 영 이쁘지 않다.
// 이 부분에 대한 해결방법은 있지만 글의 주제를 벗어나니 이 정도만!
```

<br>

### 펙토리 패턴같이 사용하면

주로 고차함수 개념이 녹아 있는 map, filter, reduce 에서 사용할 수 있다.

```javascript
let numList = [1, 2, 3, 4, 5, 6, 7];

function between(x, y) {
  return function (el) {
    return x < el && el < y;
  }
}

function include(arr) {
  return function (el) {
    return arr.includes(el);
  }
}
console.log(numList.filter(between(2, 6))); // [3, 4, 5]
console.log(numList.filter(include([1, 2, 5, 7, 10]))); // [1, 2, 5]
```

