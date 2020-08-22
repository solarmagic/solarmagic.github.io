# 솔라매직 블로그

다양한 블로그를 거쳐서 github.io로 블로그를 해본다!

## 나만의 블로그로 바꾸기

### Fork 하기

![fork](https://i.imgur.com/vXoImRp.png)

깃헙으로 가서 우상단에 star 하나 눌러 주고 포크버튼을 눌러준다.

![settings](https://i.imgur.com/hcfeI0c.png)

포크가 되면 Settings에 들어가서 이름을 `username.github.io` 처럼 바꿔주자.

### 로컬에서 빌드 해보기

1. 클론
    `git clone https://github.com/username/username.github.io.git`
2. 이동
    `cd username.github.io.git`
3. 디펜던시 설치
    `bundle install`
4. jekyll로 블로그 로컬에서 실행
    `budnle exec jekyll serve 2>/dev/null`

### 내걸로 만들기

1. 이 폴더들을 **제외한** 나머지 폴더는 **필요없는 폴더입니다**.
    - `_data`, `_include`, `_layouts`, `_posts`, `_posts`, `_sass`
    - `about`, `archives`, `assets`, `categories`, `category`, `menual`, `navigator`, `tag`, `tags`

2. 이 내용들을 **수정해야 합니다**.
    - `_include/_layout.html`의 google analytics 관련 부분 [참조 링크](https://analyticsmarketing.co.kr/digital-analytics/google-analytics-basics/2232/)
    - `_include/index.html`의 github chart이미지를 자신의 것으로 수정
    - `about/index.md`, `navigator/index.html`, `menual/index.html` 전체
    - `_config.yml`의 `title`, `description`, `author`, `url`, `avatar`, Disqus 관련 부분 [참조링크](https://devmjun.github.io/archive/addComments)
    - `_include/advertise.html` 전체 주석
    - `sitemap.xml`
    - `_posts` 폴더 내부 삭제

이러면 이제 텅빈 나만의 블로그가 완성 된다!
