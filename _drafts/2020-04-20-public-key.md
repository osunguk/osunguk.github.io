---
layout: post
title: 키페어? Key 와 암호에 대한 정리
---

EC2 인스턴스를 생성하는 과정에서 다음과 같은 창을 보게 되었다.

[키페어](https://imgur.com/gPLcZUX.png)

암호화 키에 대한 개념이 아직 정확하게 잡히지 않아서 매번 키를 발급받고 관리를 못해서 못쓰게 되는 경우가 많았고 키가 어떻게 동작하는지 정확하게 모른체 동작만 되고 이해를 건너뛰다보니 이제는 한번 정리를 해야겠다 생각이 들었다.

### 암호의 아주 기본적인 개념

2가지가 있다. 암호화, 복호화

암호화는 자신이 가지고 있는 데이터(평문)을 암호문으로 바꾸는 것이고
복호화는 거꾸로 암호문을 데이터(평문)으로 바꾸는 과정을 말한다.

암호화와 복호화의 과정을 모두 가지고 있다면 양방향 알고리즘으로 주로 key 방식의 암호화이다.
복호화를 염두해 두지 않고 암호화의 과정만 있는 경우는 단방향 알고리즘으로 해쉬 암호화 방식이 대표적이다.

두가지의 알고리즘을 차근차근 알아보자