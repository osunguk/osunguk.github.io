---

layout: post
title: 처음 사용해보는 jekyll 블로그

---

사실 jekyll 을 이용한 블로그를 시도한 게 처음은 아니다. ~~아마 한..... 5번쯤?~~ 이런저런 우여곡절 끝에 이제야 jekyll 과 github.io 저장소가 동작하는 것에 대해 이해가 돼서 이렇게 첫 글을 게시하고 있다.

지금까지 아주 기본적인 지금의 상황을 만들기 까지 어떠한 삽질을 해왔는지 이야길 해볼까 한다.

### 첫 발걸음

늘 그렇듯 처음 뭔가 해보려 할 때엔 쉬울 것 같고 하면 다 될 것 같다.

먼저 ruby 를 설치하고 jekyll 을 설치하는 건 어느 개발자라도 쉽게 할 수 있을 것이다.

![image-20200405155529275](C:\Users\osk\AppData\Roaming\Typora\typora-user-images\image-20200405155529275.png)

https://rubyinstaller.org/ 에 접속해서 설치하면 끝!

그 다음

![image-20200405155936775](C:\Users\osk\AppData\Roaming\Typora\typora-user-images\image-20200405155936775.png)

다음과 같이 루비가 설치가 되면 루비 프롬프트를 열 수 있다

프롬프트를 열고 지킬을 설치해주면 된다. ```gem install jekyll``` 명령어로 지킬을 설치해주면 끝!

![image-20200405160238559](C:\Users\osk\AppData\Roaming\Typora\typora-user-images\image-20200405160238559.png)

다음과 같이 뜬다면 성공

여기까지는 5번의 시도 모두 통과한? 큰 어려움 없는 작업이다.

### github 저장소 생성

![image-20200405193036773](C:\Users\osk\AppData\Roaming\Typora\typora-user-images\image-20200405193036773.png)

자신의 깃 허브에 add repository 를 눌러 Repository name * 에다가 아래와 같이 자신의 이름을 넣고 저장소를 생성하면 완료!! 간단하다!!

![image-20200405193006224](C:\Users\osk\AppData\Roaming\Typora\typora-user-images\image-20200405193006224.png)

위와 같이 생성하면 끝!

### 테마 적용하기

문제는 테마를 적용하기까지 의 과정이 약간 나에겐 고된 작업이었다. 

내가 사용한 테마는 [lanyon](https://github.com/poole/lanyon) 심플하고 간단하게 보이는 테마를 골랐다. 

![image-20200405193506436](C:\Users\osk\AppData\Roaming\Typora\typora-user-images\image-20200405193506436.png)

해당 테마의 깃 주소로 들어가서 우측의 ```Fork``` 버튼을 눌러 다운 받으면 된다. ~~(star 눌리는건 예의겠죠??)~~

\* *여기서 각 테마마다 설정 방법과 적용하는 방법이 각기 다를 수 있으니 해당 저장소의 README.md 파일을 꼼꼼하게 읽어주세요!!* \*

Fork를 하고 clone을 하면 디렉토리는 다음과 같습니다.

![image-20200405194638715](C:\Users\osk\AppData\Roaming\Typora\typora-user-images\image-20200405194638715.png)

간단하게 설명을 붙이면

- _includes

  - head.html
    
  - sidebar.html
    

- _layouts

  - default.html
    
  - page.html
    
  - post.html
    

- _posts
  

- public

  - /css

  - /js

  - apple-touch-icon-precomposed.png & favicon.ico

    로고 입니다

- _config.yml

- .editorconfig

- .gitignore

- 404.md

- about.md

- atom.xml

- index.html

- LICENSE.md

- README.md

### Reference

https://jetalog.net/86
https://shryu8902.github.io/_posts/2018-06-22-jekyll-on-windows/
[구글 검색](https://www.google.com/search?sxsrf=ALeKk01upV1JcU3Vs0brSQG2pzJlcdONWA%3A1586070487927&ei=14OJXvOdOJDx0gTY2Z_ADQ&q=%EC%9C%88%EB%8F%84%EC%9A%B0+jekyll+%EB%B8%94%EB%A1%9C%EA%B7%B8&oq=%EC%9C%88%EB%8F%84%EC%9A%B0+jekyll+%EB%B8%94%EB%A1%9C%EA%B7%B8&gs_lcp=CgZwc3ktYWIQAzIECCMQJ0oQCBcSDDEwLTEzMmcwZzExMUoMCBgSCDEwLTFnMGcyUPAVWPAVYLIoaABwAHgAgAF9iAHWApIBAzAuM5gBAKABAaoBB2d3cy13aXo&sclient=psy-ab&ved=0ahUKEwiz5ZWA3dDoAhWQuJQKHdjsB9gQ4dUDCAw&uact=5](https://www.google.com/search?sxsrf=ALeKk01upV1JcU3Vs0brSQG2pzJlcdONWA%3A1586070487927&ei=14OJXvOdOJDx0gTY2Z_ADQ&q=윈도우+jekyll+블로그&oq=윈도우+jekyll+블로그&gs_lcp=CgZwc3ktYWIQAzIECCMQJ0oQCBcSDDEwLTEzMmcwZzExMUoMCBgSCDEwLTFnMGcyUPAVWPAVYLIoaABwAHgAgAF9iAHWApIBAzAuM5gBAKABAaoBB2d3cy13aXo&sclient=psy-ab&ved=0ahUKEwiz5ZWA3dDoAhWQuJQKHdjsB9gQ4dUDCAw&uact=5))

