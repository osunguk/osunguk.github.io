---

layout: post
title: 처음 사용해보는 jekyll 블로그

---

사실 jekyll 을 이용한 블로그를 시도한 게 처음은 아니다. ~~아마 한..... 5번쯤?~~ 이런저런 우여곡절 끝에 이제야 jekyll 과 github.io 저장소가 동작하는 것에 대해 이해가 돼서 이렇게 첫 글을 게시하고 있다.

지금까지 아주 기본적인 지금의 상황을 만들기까지 어떠한 삽질을 해왔는지 이야길 해볼까 한다.

### 첫 발걸음

늘 그렇듯 처음 뭔가 해보려 할 때엔 쉬울 것 같고 하면 다 될 것 같다.

먼저 ruby 를 설치하고 jekyll 을 설치하는 건 어느 개발자라도 쉽게 할 수 있을 것이다.

![image-20200405155529275](C:\Users\osk\AppData\Roaming\Typora\typora-user-images\image-20200405155529275.png)

https://rubyinstaller.org/ 에 접속해서 설치하면 끝!

그다음

![image-20200405155936775](C:\Users\osk\AppData\Roaming\Typora\typora-user-images\image-20200405155936775.png)

다음과 같이 루비가 설치가 되면 루비 프롬프트를 열 수 있다

프롬프트를 열고 지킬을 설치 해주면 된다. ```gem install jekyll``` 명령어로 지킬을 설치해 주면 끝!

![image-20200405160238559](C:\Users\osk\AppData\Roaming\Typora\typora-user-images\image-20200405160238559.png)

다음과 같이 뜬다면 성공

여기까지는 5번의 시도 모두 통과한? 큰 어려움 없는 작업이다.

### github 저장소 생성

![image-20200405193036773](C:\Users\osk\AppData\Roaming\Typora\typora-user-images\image-20200405193036773.png)

자신의 깃 허브에 add repository 를 눌러 Repository name * 에다가 아래와 같이 자신의 이름을 넣고 저장소를 생성하면 완료!! 간단하다!!

![image-20200405193006224](C:\Users\osk\AppData\Roaming\Typora\typora-user-images\image-20200405193006224.png)

위와 같이 생성하면 끝!

### 테마 적용하기

문제는 테마를 적용하기까지의 과정이 약간 나에겐 고된 작업이었다. 

내가 사용한 테마는 [lanyon](https://github.com/poole/lanyon) 심플하고 간단하게 보이는 테마를 골랐다. 

![image-20200405193506436](C:\Users\osk\AppData\Roaming\Typora\typora-user-images\image-20200405193506436.png)

해당 테마의 깃 주소로 들어가서 우측의 ```Fork``` 버튼을 눌러 다운 받으면 된다. ~~(star 눌리는 건 예의겠죠??)~~

\* *여기서 각 테마마다 설정 방법과 적용하는 방법이 각기 다를 수 있으니 해당 저장소의 README.md 파일을 꼼꼼하게 읽고 사용하시길 바랍니다!!* \*

```Fork``` 를 하고 ```clone```을 하면 디렉토리는 다음과 같다.

![image-20200405194638715](C:\Users\osk\AppData\Roaming\Typora\typora-user-images\image-20200405194638715.png)

간단하게 설명을 붙이면

- _includes

  - head.html
    
    화면상 고정되어 있는 head
    
    CSS 와 Icon 과 RSS 를 link

  - sidebar.html
    
    화면 옆쪽에 뜨는 sidebar
    
    

- _layouts

  - default.html
    
    모든 화면의 기본을 잡아주는 html, head와 sidebar를 불러오고 content와 sidebar에 관한 script를 가지고 있다.
    
  - page.html
    
    페이지의 기본 틀 (사이드바에 들어가는 page)
    
  - post.html
    
    게시물의 기본 틀

- _posts
  

글을 작성할 때 해당 디렉토리에 md 파일을 생성해서 글을 쓴다.

  제목을 쓸 때는 YYYY-MM-DD-post-name.md 형식으로 작성하면 된다.

- public

  - /css

  - /js

  - apple-touch-icon-precomposed.png & favicon.ico

    로고

- _config.yml

  jekyll이 동작하기 위한 여러 설정값들이 있는 중요한 파일!!

- .editorconfig
  에디터의 설정을 정해주는 파일로 charset, indent_style 등 파일의 일관성을 유지할 수 있게 도와준다.

- .gitignore

  깃 저장소에 올리지 말아야 할 데이터나 (key 값)  불필요한 데이터 (cache 데이터) 들이 git 저장소에서 무시하게 설정하는 파일

- 404.md

  존재하지않는 주소로 들어올 경우 표시되는 md 파일

- about.md

  layout이 page 로 sidebar에 표시, 해당 링크를 누르면 about.html 이 불려오면서 md 파일에 적어둔 글이 보이게 된다.

- atom.xml

  RSS 와 비슷한 기능을 하는 파일로 구독을 한 사람에게 Feed 하기 위한 파일

- index.html

  baseurl 로 들어가면 표시되는 화면으로, home 화면으로 title이 잡혀있다

- LICENSE.md

  라이센스 관련한 md 파일

- README.md

  깃허브 저장소에 프로젝트 README 파일

- _site

  ```jekyll serve```  명령어를 실행하면 해당 디렉토리를 만들어 로컬 호스트로 변경사항을 확인할 수 있게 도와준다. 다만 .html 파일이나 .md 파일이 변경되었을 때 바로바로 적용이 되며 config.yml 파일 같은 경우는 jekyll 서버를 껐다가 다시 가동해 확인해야 한다.

  _site 디렉토리를 다시 만들고 싶다면 ```jekyll build``` 명령어를 실행시키면 된다.

  

### 마무리

http://themes.jekyllrc.org/ 로 들어가면 정말 다양한 Theme 를 볼 수 있다.

각각의 Theme 마다 특징들이 있고, 각자만의 구조를 가지고 있기 때문에 해당 Theme의 document 를 꼼꼼하게 읽어 보기를 추천한다.

jekyll 이라는 정적 사이트 생성기에 대한 이해가 없는 상태로 일단 되게 해보자는 마음으로 달려들었다가 꽤 많은 시간을 허비하게 되었다.

약간은 답답하겠지만 천천히 차근차근 한 단계씩 정복?해 나가다 보면 충분히 할 수 있을 거라 생각한다.

아직 많이 왜소하고 부족한 게 많은 블로그이지만 하나씩 커스텀 하는 맛이 꽤 쏠쏠하다. 테마가 가지고 있는 틀을 과감하게 벗어 버릴 수도 있고, 자기만의 특별한 layout이나 css 요소들도 직접 구현할 수 있다.



### Reference

https://jetalog.net/86

https://shryu8902.github.io/_posts/2018-06-22-jekyll-on-windows/

[구글 검색](https://www.google.com/search?sxsrf=ALeKk01upV1JcU3Vs0brSQG2pzJlcdONWA%3A1586070487927&ei=14OJXvOdOJDx0gTY2Z_ADQ&q=%EC%9C%88%EB%8F%84%EC%9A%B0+jekyll+%EB%B8%94%EB%A1%9C%EA%B7%B8&oq=%EC%9C%88%EB%8F%84%EC%9A%B0+jekyll+%EB%B8%94%EB%A1%9C%EA%B7%B8&gs_lcp=CgZwc3ktYWIQAzIECCMQJ0oQCBcSDDEwLTEzMmcwZzExMUoMCBgSCDEwLTFnMGcyUPAVWPAVYLIoaABwAHgAgAF9iAHWApIBAzAuM5gBAKABAaoBB2d3cy13aXo&sclient=psy-ab&ved=0ahUKEwiz5ZWA3dDoAhWQuJQKHdjsB9gQ4dUDCAw&uact=5](https://www.google.com/search?sxsrf=ALeKk01upV1JcU3Vs0brSQG2pzJlcdONWA%3A1586070487927&ei=14OJXvOdOJDx0gTY2Z_ADQ&q=윈도우+jekyll+블로그&oq=윈도우+jekyll+블로그&gs_lcp=CgZwc3ktYWIQAzIECCMQJ0oQCBcSDDEwLTEzMmcwZzExMUoMCBgSCDEwLTFnMGcyUPAVWPAVYLIoaABwAHgAgAF9iAHWApIBAzAuM5gBAKABAaoBB2d3cy13aXo&sclient=psy-ab&ved=0ahUKEwiz5ZWA3dDoAhWQuJQKHdjsB9gQ4dUDCAw&uact=5))

https://jamiekang.github.io/2017/04/28/working-jekyll-locally/