---
layout: post
title: 코드 스테이츠 주차
categories: [codestates]
---

코드 스테이츠를 통해 배운 것을 정리하는 post

> 무엇이든 보고 듣기는 쉽지만
> 자기 것으로 만드는 것엔 노력이 필요하다.

<br>

## 월요일

1. var, let, const 가 선언되면

var 는 window로 참조가 되는데 let, const 는 참조가 안되서 헬프데스크에 질문을 했다!

그리고 문제가 해결되었다! [해당이슈](https://github.com/codestates/pre-help-desk/issues/2690)

2. 고차함수

말그대로 고차원적인 생각이 필요한 파트였다. return 관리를 아주 잘해야겠다는 생각이 들었다.

3. 고차함수로 만든 배열 메서드들

- map
- filter
- reduce

실제로 회사에 있을 때, 사용을 해본 메서드들이였다.

Fiter 이녀석은 true 값을 반환하고 나머지는 무시하면 알아서 처리하는데

map, reduce 이 친구들은 모든 경우를 다 처리해줘야 ~~아몰랑~~ undefined 를 발생하지 않는다.

4. 휴식시간 효율적으로 사용하기

정규 수업시간이 끝나고 잠깐 눈이라도 붙일겸 15분 타이머를 맞춰두고 누웠다가

2시간 반이라는 시간이 지난 뒤에 눈을 떠버렸다....

쉬는건 간단히 엎드려서 쉬기!

<br>

## 화요일

1. 기본 알고리즘

현재시각 새벽 2시30분 20번 문제까지 모두 완성하고 마침

코플릿에서 푸는 문제들을 따로 파일로 만들어서 관리에 용이하게 만들었다. (이전꺼는 ... 어떻하지?)

2. Quokka 익스탠션

굉장히 유용하게 잘 쓰고 있다. console.log 로 디버깅하기도 편하고 코드 흐름도 잡을 수 있다

3. 코드 스테이츠 토크 세션

8시에 참석해서 22기 분의 생생한 취업 이야기를 들었다.

기억에 남는 것

- 재호님을 열심히 괴롭히자
- 영문 이력서도 고려해보자
- 회사를 알기전에 나 자신을 알자
- 1년차 개발자 뚝배기 깨자

4. 코드 컨벤션

이번 lesson 으로 있었는데 양이 생각보다 방대해서 정리할 필요가 있다!

<br>

## 수요일

1. DOM 다루기
2. emmet

HTML 작업을 할때 아주아주아주아주아주 간편하게 작업할 수 있게 도와주는 기술?을 배웠다

3. 여러 익스텐션

Auto Rename Tag : html 태그를 고치면 나머지 쪽도 동시에 변경

Bracket Pair Colorizer : 괄호를 매칭된 것끼리 같은색으로 표시

CSS Peek : html 에서 클래스를 command 클릭하면 해당 선택자의 css 로 이동

HTML to CSS autocompletion : css 에서 해당 id, class 설정할 수 있는걸 자동 완성시켜주는 기능

Live Server : 변동사항을 새로고침안해도 적용시켜줌

<br>

## 목요일

1. 유효성 검사

코드를 짜면서 느껴진게 많아서 노션으로 긴 글을 남겼다. [여기](https://www.notion.so/91c72e8e28504b50b7a03e73262b1c9a)

2. VScode 애용하는 단축키 정리

너무 기본적인 단축키를 제외한 것들 [여기](https://www.notion.so/VScode-140a7d105554450ab9216f5971e47c18) 에 적어뒀는데 계속해서 추가해서 사용할 예정!

혹시나 notion 사용하시는 분들 중에 꿀같은 단축키 아시는분 댓글로 남겨주세요 ㅎㅎ

3. 트위틀러 처음으로 돌아가기

처음 만들었던 html 과 css 가 너무 형편이 없어서 (그만큼 빠른 속도로 성장중인가 보다)

페어분과 몇마디만에 ~~폐기~~ 초기화를 시켜버렸다. 너무 속시원했다. 그러곤 차근차근 쌓아 가는데 이쁘게 잘 뽑혔다.

html 과 css 구조 잡는 것에 대한 심도있는 블로깅을 해야겠다는 생각이 들었다.

<br>

## 금요일

**:christmas_tree: ​Merry Christmas!! :christmas_tree:**

<br>

## 주말

1. 고차함수 - 더 생각해 볼 주제 공부

- MapReduce 학습하기
- 자바스크립트에서 커링(currying)과 클로져(closure)의 차이 이해
- 선언형 프로그래밍(declarative programming)과 절차형 프로그래밍(imperative programming)의 차이
  - 배열 메소드를 통해 이해하기
- 함수의 조합(function composition)에 대해 학습하기 (javascript function composition)

를 정리했고, 배열 메소드를 통해 이해하기를 제외하고 전부 공부를 했다.

2. DOM 이해하기

모든 html 태그를 순환하는 코드를 작성했다.

```javascript
function consoleLogAllElement() {
  console.log('모든 태그를 출력하는 함수입니다!');
  const body = document.getElementsByTagName('body');
  const elements = body[0].children;

  console.log(elements);

  cycle(elements);

  // console.log(body[0].childNodes); 
  // childNodes 는 모든 노드를 불러 오는듯 보인다
  // text 라는 요소가 있는데 정확히 어떤 부분인지 모르겠다

  // console.log(body[0].children); 
  // children 은 원하는 기능인 하위 element의 요소를 리턴한다.

  // console.log(body[0].childElementCount); 
  // 직계자식들의 엘리먼트의 숫자를 반환
}

function cycle(elements) {
  for (element of elements) {
    if (isHaveChildren(element)) {
      console.log(element);
      cycle(element.children);
    } else {
      console.log(element);
    }
  }

}

function isHaveChildren(e) {
  if (e.childElementCount > 0) {
    return true;
  } else {
    return false;
  }
}


consoleLogAllElement();
```

정확한 코드인지는 모르겠으나 모두 출력하긴한다. 재귀 개념을 도입해봤는데 만족스럽다.

<br>

3. DOM 조작하기

4. JS 주제 블로깅 하나 하기!!

- [ ] 하나
- [ ] 둘
- [ ] 셋

