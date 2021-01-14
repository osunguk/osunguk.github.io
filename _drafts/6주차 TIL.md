---
layout: post
title: 코드 스테이츠 6주차
categories: [codestates]
---

코드 스테이츠를 통해 배운 것을 정리하는 post

> 무엇이든 보고 듣기는 쉽지만
> 자기 것으로 만드는 것엔 노력이 필요하다.

<br>

- 학습할 내용

(화요일) ~~git 명령어 branch 에 대해서 정리하기~~

git 연습사이트 마지막까지 다 풀기 (원격작업 merge 까지 진행)

(화요일) ~~자바스크립트 info 페이지 정리 (1개)~~ 두개 더 하기 

git rebase 정리하기

<br>

## 월요일

#### 이머시브 OT

확실히 pre 코스보다 다루는 주제의 난이도가 훨씬 높아진 것 같다. 점점 전공자로 누릴 수 있는 메리트가 없어지는 느낌이 들기 시작한다. 조금 더 열심히 할 필요가 있는 것 같다.

<br>

#### Git Flow 연습

동기분이 [이런 사이트](https://learngitbranching.js.org/?locale=ko) 알려주셔서 git 명령어를 연습하는데 많은 도움이 됬다.

나중에는 GUI 를 지원하는 sour tree 같은걸 사용하겠지만 터미널 명령어 연습하는 것도 지금으로선 좋은것 같다.

[노션](https://www.notion.so/git-3e122b941ba54a11903d4d746bc2f826) 에 git 명령어와 개념에 대해서 정리중이다.

<br>

#### 이진탐색 알고리즘 구현

[3일 동안 헤매는 문제](https://programmers.co.kr/learn/courses/30/lessons/64062) 를 풀다가 도저히 이대로가다간 시간만 버릴것 같아서 여기서 효율성 알고리즘으로 사용하는 이진 탐색 알고리즘부터 구현하기로 했다.

이진 탐색 알고리즘의 시간 복잡도는 순차탐색이 N 제곱인 반면 로그2N이다. 

0 < target < 2000000 중 숫자 346323를 21번의 시도만에 찾는 굉장히 효율적인 알고리즘이다. 이를 토대로 여러가지 알고리즘에 필요한 역량들을 키워나가야 겠다.

<br>

## 화요일

#### 화살표 함수

#### 키워드 `this`

#### call, apply, bind 메서드

3개를 모조리 정리하는데 꽤 오랜 시간이 걸렸다 ㅜ

전부 연관이 있는 주제라 하나의 [노션](https://www.notion.so/Modern-JavaScript-Koans-40074ae2b27f4b6d813de31f32ba7789) 에다가 정리를 해뒀다

> This 는 자신이 참조할 객체를 찾아다니는 녀석
>
> call 과 apply 는 참조할 객체를 명시해주고 인자도 넘겨준다
>
> bind는 어떤녀석을 참조해야하는지 알려주고 묶은걸 함수로 반환해준다
>
> 화살표 함수는 this 를 결정하지 않는데 this를 잃으면 가장 가까운 객체를 찾아서 지정해준다

<br>

#### Prettier, ESLint

코드 컨벤션을 관리해주는 익스텐션인데 실시간으로 검사해주고 저장시에 자동으로 적용시켜주는 아주 강력한 기능들이 담겨져 있다.

<br>

#### Git Branch

아직은 Master 브랜치 하나만을 이용해서 진행을 해서 다양한 브랜치들을 다루는법에 대한 필요성을 느끼지 못하고 있다. 나중에 프로젝트를 시작하기 전에 브랜치 사용 전략들을 고려해봐야겠다

<br>

#### Git Log

깃 로그를 보는 명령어 인데 정말 다양한 옵션들이 있어서 내가 원하는 커밋 이력들, 다양한 필터링과 포맷으로 볼 수 있었다.

<br>

#### TIL 작성법 변경... ㅎ내맘대로 해보기

요일마다 내일작업할 내용을 적는게 귀찮아서 맨 위에다가 전부 적고 해결하면 (요일이름)~~작업한내용~~ 이런식으로 작성을 해보려고 한다.

<br>

## 수요일

#### HA 리팩토링

ES6 의 주요 문법 5가지

- 구조 분해 할당 : 파라미터 관리나 특정 인덱스의 값을 받아올 때 편하다
- 전개 연산자 : console.log(...['말', '해', '뭐', '해']);
- 화살표 함수 : this 만 안쓰면 착한 친구
- 템플릿 레터럴 : str + ' ' + str 이런거 안해도 된다!!
- for ... of loop : 더 이상 귀찮은 let i = 0 그만

문제마다 적용할 수 있는 기술들을 고려해보고 실제로 써먹어 봤다. 프로그램 언어가 이렇게 발전되어 가는구나 느꼈다.

<br>

#### Linting

지금까지 코드 컨벤션에 대해서 그리 크게 필요성과 중요성을 못 느끼고 있었는데 이번 스프린트를 진행하면서 많이 느꼈던것 같다.

각자의 코드 스타일이 있고 습관들이 다양하다보니 프로젝트를 진행할 때 충돌이 불가피하다고 느껴졌다. 코드 작성에 대한 팀의 규칙을 만들고 쓰는게 가장 좋겠지만 습관이라는게 그리 쉽게 바뀌지 않는다.

Linter 를 이용해서 규칙을 공유하고 적용시켜 하나의 통일된 코드를 작성할 수 있는 기술이 있다는게 다행이다.

ESLint 와 Prettier 를 사용하는데 option 들이 정말 많고 프로그램의 문법이 많은만큼 이에 대한 작성 규칙도 정비례 하다보니 그렇게 되지 않았나 싶다.

일단 기본적으로 지원하는 default formater 를 이용해 보편적으로 사용하는 코드 컨벤션을 숙지 중이다.

<br>

#### notice 에 올려주신 `this` 관련 영상

영상을 보고 조금 더 입체적으로 `this` 를 볼 수 있게 되었다

```javascript
function test() {
  console.log(this)
};
// test() === window.test()
// 위의 두 경우가 같기 때문에
// 결국 함수 호출도 method 호출의 한 부분이다
```

```javascript
let obj = {
  fn: function(a, b) {
    return this;
	}
};

let obj2 = {
  method: obj.fn
};

console.log(obj.fn() === obj); // true
console.log(obj2.method() === obj); // true

// 첫번째 경우는 쉽다
// 두번째 경우가 약간 헷갈릴 수도 있는데
// 단순하게 함수가 실행됬을 때 . 의 왼쪽에 있는 객체를 this 로 지정
// 함수를 치환하고 값을 계산하고 그런거 필요없다.
```

```javascript
class Rectangle {
  constructor(width, height) {
    this.width = width;
    this.height = height;
  }
  
  getArea() {
    return this.width * this.height;
  }

  printArea() {
    console.log('사각형의 넓이는 ' + this.getArea() + ' 입니다');
  }
  
  printSync() {
    // 즉시 사각형의 넓이를 콘솔에 표시합니다
    this.printArea();
  }
  
  printAsync() {
    // 1초 후 사각형의 넓이를 콘솔에 표시합니다
    setTimeout(this.printArea, 2000);
    // 콜백함수가 실행되면 this 의 값이 전역 객체로 설정된다.
    // 해결방법 1 : 메서드 호출시 this 는 인스턴스를 가리키므로 인스턴스와 바인딩 시켜주면 해결 가능
    setTimeout(this.printArea.bind(this), 2000);
    // 해결방법 2 : 함수실행 시 전역으로 설정된 this 를 담어뒀던 self 값으로 초기화 시켜줘서 해결 가능
    let self = this;
    setTimeout(function() {
      self.printArea(); 
    }, 2000)
    // 해결방법 3 : this 가 상위 context의 this 를 가리키기 때문에 상위 객체인 Rectangle의 인스턴스를 가리킨다.
    setTimeout(() => {
      this.printArea();
    }, 2000)
  }
}

let box = new Rectangle(20, 40);
```

<br>

## 목요일



## 금요일



## 주말
