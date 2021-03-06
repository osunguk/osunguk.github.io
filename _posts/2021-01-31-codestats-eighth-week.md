---
layout: post
title: 코드 스테이츠 8주차
categories: [codestates]
---

코드 스테이츠를 통해 배운 것을 정리하는 post

> 무엇이든 보고 듣기는 쉽지만
> 자기 것으로 만드는 것엔 노력이 필요하다.

<br>

- 학습할 내용

자바스크립트 인포 정리 ~~(목요일)2개~~

Figma 튜토리얼 진행 

~~HA 전에, oop 복습, 자료구조 복습 & HA 잘 치기~~

깊이 우선, 너비 우선 자료 정리

<br>

## 월요일

#### N Queens

여러운 알고리즘 문제라고 익히 들어서 어렵겠거니 했는데 너무 어려워서 꽤나 애를 먹었다.

<br>

## 화요일

#### 재귀함수 복습

[재귀함수 노션 정리](https://www.notion.so/osunguk/dbf52a7f3635492b8f49cf3f24404b4c) 한 걸 동기 채널에 올려 공유를 했다. 노션의 댓글 기능으로 피드백을 받고 바로바로 수정을 할 수 있는 기능을 처음 사용했는데 굉장히 만족 스럽다.

아직 완벽하게 재귀를 이해한건 아니지만 전체적으로 컴퓨터가 어떻게 깊이 우선 탐색을 실행하고 탈출구를 만나면 그 뒤에는 어떻게 동작을 이어나가는지에 대해서 조금씩 이해가 가기 시작했다.

<br>

#### 프로그래머스 깊이/너비 우선 탐색 첫번째 문제

재귀 함수를 복습하고 프로그래머스에서 해당 개념을 사용하는 문제가 있어서 풀어봤는데 굉장히 잘 풀렸다. 배웠던 재귀 템플릿을 생각하면서 전체적인 수도코드를 작성하고 살을 채워 나갔다.

<br>

#### 자바스크립트는 왜 그 모양일까?

동기분이 책 내용이 괜찮다고 해서 사서 이번주 월요일에 받았는데, 시간이 영 안나서 안 읽고있다가 잠시 짬이라도 내서 인트로 부분을 읽었다. JSON을 만드신 장본인분이 쓰신 책이고 JS 뿐만 아니라 PL 에 대해서 굉장한 내공이 있으시다는걸 글로만 봐도 느껴질 정도다.

내용 자체가 굉장히 유쾌하게 써져있어서 가독성도 너무 좋고 우리가 어떻게 더 현명하게 프로그래밍 언어들 다룰 수 있을지에 대한 고민이 많이 담겨있는거 같아서 어서 빨리 읽고 싶다.

<br>

#### 줌방 CPU 속도 대결

```javascript
console.time();
console.timeEnd();
```

위의 두 함수를 실행시키면 연산에 걸린 시간을 얼추 알 수 있어서 누구의 컴퓨터의 연산이 빠른지 베틀이 붙었었다.

결국 최신 맥북 M1 을 가진분이 1등을 먹었고 나는 2등을 먹었는데 굉장히 내 맥북 성능에 대해서 만족스러웠다.

<br>

#### 배열을 객체로 담으면?

```javascript
let x = [1,2,3,4];
let y =  {...x};
console.log(y); // {0: 1, 1: 2, 2: 3, 3: 4}
```

알아서 인덱스값이 key 로 인덱스 안에 있는 값이 value 로 들어간다.

<br>

## 수요일

#### HA

무사히 시험을 마치게 되었다. 구조 분해 할당 부분에서 생각보다 애를 많이 먹었다. 바로 밑에 적힌 소주제에 정리를 했다. 재귀의 비중이 생각보다 컸고 이제는 어느정도 원하는 모양을 잘 만들어 낼 수 있어졌다.

<br>

#### 객체를 복사하는 3가지 방법

- 전개 연산자 사용하기
- Object.assign({}, 복사대상)
- JSON

3가지 복사들의 장단점? 이 있으며 얕은 복사, 깊은 복사에 대해서도 정리를 했다.

<br>

#### 10시 취침

잠을 많이 못자다보니 피로가 계속 쌓이는 느낌이 든다. HA 전까지는 어떻게 어떻게 버티다가 시험이 끝나니까 긴장도 풀렸다. 시험을 마치고 대략 4시간 정도 잠을 잤다. 일어나서 공부를 하려해도 안되고 집중도 안되서 오늘은 그냥 놀아야겠다 마음을 먹었다, 그런데 놀 기력도 없어서 10시에 바로 취침을 해버렸다. ( 어제 못쓴 TIL 을 오늘 5:04 에 작성중에 있다... ㅋㅋ )

수면관리를 조금 더 신경써서 해야겠다. 늦게까지 에너지를 쏟아내며 뭔가를 하기보단, 일찍 일어나서 맑은 머리로 작업을 하는게 조금 더 생산성이 좋아질것 같다.

<br>

## 목요일

#### Date 객체

가장 헷갈리는 부분이 UTC 부분이였는데 한국 시간은 +09:00 만 해주면 된다는 결론이 나서 조금 이해가 되었다. 각각의 나라마다 시차도 있고 시간 데이터를 다룰때는 필수적으로 timezone ? 정보가 필요하겠다.

<br>

#### JSON과 메서드

단순히 stringify 와 parse 만 있는줄 알았는데 매개변수로 다양한 동작들을 시킬 수 있다는걸 알았다.

<br>

## 금요일

#### arguments 객체

파라미터를 받아오는 유사배열이다. 화살표 함수를 사용할 때는 가지지 않는다는 것도 알게 되었다.

<br>

#### 스코프, 클로저, 렉시컬 환경

스코프 부분은 이제 대부분 알았다고 생각했는데 조금 더 딥하게 들어가니 렉시컬 환경에 대해서 자세히 배우게 되었다. 함수가 선언되면 이에 해당하는 렉시컬 환경이 생성되고 그 함수가 선언된 환경을 `[[environment]]` 에 담겨서 외부 참조로 두는 부분도 알게 되었다.

<br>

#### 전역 객체

`globalThis` 라는 새로운 명세에서 런타임 상관없이 전역객체를 가리키는 객체를 만들었다고 한다. 아직 완전히 안정화 되진 않았지만 계속해서 진행되는 것 같다.

<br>

## 주말

#### 기명함수

기명함수는 말 그대로 이름이 있는 함수를 뜻한다. 보통 함수를 표현식으로 사용하면 `let func = function(){}` 식으로 많이 사용하는데 기명 함수를 이용하면 생성한 함수에 대한 참조통로?가 하나더 생긴다. 이를 이용해서 

```javascript
let hamsu = function func(txt) {
	if(txt) {
		console.log(`${txt}`);
	} else {
		func("empty parameter"); // empty parameter
//  hamsu("empty parameter"); // TypeError: sayHi is not a function
	}
}

let work = sayHi;
hamsu = null;

work();
```

위와 같이 hamsu 에 null 값으로 초기화가 되어도 생성한 함수에 대한 참조가 남아있기 때문에 에러없이 사용할 수 있다.

<br>

#### `new Function`

함수를 만드는 secret한 방법, 함수의 내용이 스트링으로 들어오는 경우 사용한다. (아마 쓸일이 있을까?)

<br>

