---
layout: post
title: 코드 스테이츠 1주차

---

코드 스테이츠를 통해 배운 것을 정리하는 post

> 무엇이든 보고 듣기는 쉽지만
> 자기 것으로 만드는 것엔 노력이 필요하다.

<br>

### 월요일

1. **JS 에서 false 한 값**

아래의 8개의 값은 불리언 문맥에서 false 값으로 평가되는 값이다.

- false : 보통 사용하는 키워드
- 0 : 숫자 0
- -0 : 음수 0
- 0n : <u>BigInt</u> 불리언으로 사용되면 숫자 0과 같은 취급
- "", '' : 빈 string
- null : 아무런 값이 없음
- Undefined : 원시값으로 선언한 후 값을 할당하지 않은 변수 혹은 값이 주어지지 않은 인수에 자동으로 할당되는 값
- <u>NaN</u> : Not-a-Number

<br>

1-1. BigInt

2^53 - 1보다 큰 정수를 표현할 수 있는 내장 객체

Math 객체의 메서드와 사용할 수 없고 Number과 혼합해 연산할 수 없다.

<br>

1-2. NaN

만드는 법 5가지

- 이게숫자냐? > parseInt('가나다라'), Number(undefined) 
- 허수를 만들어 버리면 > Math.sqrt(-1) 
- NaN 바이러스 > 7 + NaN
- 계산해보려무나 > 0 * Infinity
- 문자열은 더하기만 해주세요 ㅠ > "가 " / 3

위의 여러가지 경우가 하나의 NaN 을 만들어 내서 그런지

```javascript
NaN === NaN // false 값
isNaN(NaN) // true 값
```

이런 결과를 만들어 낸다.

<br>

2. debugger 사용하기

디버거를 breakpoint 와 비슷하다고 봐도 되겠다. 검증하고 싶은 코드 위에 debugger 라고 쓰면 쓰인곳에서 코드의 흐름이 멈춘다.

값이 어떻게 할당되는지 볼 수 있다. 참고로 맥북에서 스텝 바이 스텝을 보려면 function 키를 누르고 f9를 누르면 한단계씩 진행된다(~~이거 찾느라 얼마나 고생을....~~)

<br>

### 화요일

1. var 코드는 레거시코드 ~~라떼코드~~

왜 쓰지 말라고 추천하는지 찾아 보았다. [참고한 블로그1](https://www.daleseo.com/js-var-issues/) [참고한 블로그2](https://velog.io/@solmii/Java-Script%EC%9D%98-variable)

문제는 *Hoisting* 였다. var 키워드로 변수를 선언하면 해당 변수가 속한 scope의 최상단으로 올려버린다.
그리고 함수의 범위가 block 범위가 아니라 function 범위다!!

이게 무슨 말이냐? 

 ```javascript
function test(){
    console.log(x);
    {
			var x= 2;
    }
    console.log(x);
}
test();

// 이 코드의 결과값은
// undefined
// 2
// ???
// js 는 위의 코드를 아래와 같이 해석한다

function test(){
  var x;
  console.log(x);
  {
    x = 2;
  }
  console.log(x);
}
test();
 ```

~~나는 블럭안에 가뒀는데 가둘수가 없어요~~

블록 스코프를 무시하기 때문에 예상치 못한곳에서 변수가 참조되고 값이 들어가고 읽히는 일이 벌어지는 난장판이 만들어진다.

이를 해결하기 위한 키워드!!! let 과 const 앞의 두 키워드는 block scope 를 가지기 때문에 위와 같은 초유의 사태를 막을 수 있다.

또다른 하나의 방법 **"use strict"** ~~엄격 모드!!~~

기능은 다음과 같다

- 설렁설렁 넘어갔던 에러들 안봐줌
- JS 엔진의 최적화 작업을 방해하는 요소를 바로잡음
- 차기 버전들에서 정의 될 문법을 금지

이대로 들으면 와닿지 않으니까 예시로 봅시다

- 선언하지 않은 변수 사용불가
- 읽기 전용 속성에 할당 불가능
- 한 속성에 여러 정의가 불가능
- 매개변수 이름 중복 불가능

찾아보니 너무 많다... [여기](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Strict_mode) 있으니 구경이라도 다녀오자 암튼 엄격한거임

<br>

### 수요일

1. id vs class

id 는 고유한 값으로 하나밖에 가지지 못한다. css 선택자 기호는 #

class 는 그룹명? 이라고 보면 이해가 쉬울듯하다. css 선택자 기호는 .

class 가 중복으로 사용 가능하므로 많이 쓰이는 듯하다.

<br>

2. div vs section

실무에서 일을하는 누나님께 여쭤보니 압도적으로 div 승리....

그래도 section 사용법은 알아두기!

<br>

### 목요일

여태 수많은 for 문을 쓰면서 오해하던 부분이 있었다

```javascript
let x = 3
for(let i=0; i<5; i++){
  let check = true;
  if(i === x){
    check = false;
  }
  if(check) console.log('hello')
}
```

단순한 for 문이다. i 가 x 와 값이 같아지면 hello 를 출력하지 않도록하는 코드이다.

여기서 나는 한가지 잘못 알고있었던 부분이 for 문 안에 있는 check 변수가 for 문이 돌아가는 동안 계속해서 살아있는줄 알았다.... 

코드로 설명하자면

```javascript
let x = 3
i = 0
let check = true;
if(i === x){
	check = false;
}
if(check) console.log('hello')
// 원래는 여기서 check 변수는 선언이 헤재된다 (나는 안없어지고 남아있는줄 ...)
i = 1
let check = true;
if(i === x){
	check = false;
}
if(check) console.log('hello')
// 생략
```

위와같이 같은 이름의 변수가 계속 선언 할당되어서 오류를 뿜어 낼것이다 라고 잘못 알고 있었다!! 아무튼 지금은 아주 잘 이해했다

<br>

### 금요일

계산기를 만들었습니다

수강생분들이 모두 있는 자리에서 수줍게 이것저것 꾸며본 계산기를 발표했다.

간단하게 칭찬받은 부분만 빨리 짚고 넘어가겠다 ㅎㅎ 

1. 주어진 해결 방식에서 벗어나 조금 더 나은 해결방법을 찾아냈다.

여기 글로는 설명할 수는 없지만 기존의 해결방법으로는 계산기가 0 + 9 = 9 연산이 불가능 했는데 다른 방법을 통해 가능하게 만들어서 칭찬을 받았다

2. 조금 더 안정감있는 코드 작성

```javascript
let result = '';

result = calculate(firstOperend.textContent, operator.textContent, secondOperend.textContent);

return result;
```

사실 return 뒤에 할당받는 값을 바로 넣어버릴 수 있지만 유지보수적인 측면에서 좋다고 하신것 같다.

해당 코드에서 오류가 났을 때 result에 값이 정확히 들어갔는지 확인할 수 있고 해당 값에 대한 의미를 추가할 수 있다!

<br>

### 주말

- 1년 회고 작성
- first week TIL 작성