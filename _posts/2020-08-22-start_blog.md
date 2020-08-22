---
title:  "github.io 로 블로그 새 단장"
date:   2020-08-22 00:20:00
categories:
- Daily
tags:
- Documentaion
- Blog
---

> 개발자라면 기술 블로그 하나쯤은 운영해야하지 않겠는가?

## 바꾸게 된 계기

원래도 기술 블로그가 있었지만 다음 블로그, 티스토리, Blogger를 사용해봤으나 뭔가 다 탐참치 않았다.

결정적으로 오늘, 2020년 8월 22일 SCPC 1라운드 후기를 올리려고 하는데 MathJax가 제대로 안 먹는 문제가 생겼다. 이번 기회에 블로그를 새로 단장하기로 했다.

`cgiosy`님의 추천을 받고 github.io로 옮기기로 햇다.

## github.io 시작하기

### Fork할 블로그 정하기

처음부터 만드는 것보다 이미 잘만들어져있는걸 fork하는게 여러모로 좋다.

내가 원하는건 다음과 같았다.

- 마크다운 지원
- LaTeX(MathJax) 지원
- 코드가 예쁘게 나와야 함

어찌보면 PS하는 사람이면 저정도는 이미 기본세팅으로 잘 해놨을거라서 PS 블로그 중에선 가장 포스팅~~과 코드 표절~~이 활발한 [나정휘님 블로그](https://justicehui.github.io/)를 포크하기로 맘 먹었다.

> 사실 생각나는 github.io PS 블로그가 `wookje.dance`랑 `justicehui.github.io` 뿐이라 별 고민 안하고 골랐다.

### Fork 하기

![fork](https://i.imgur.com/EBiNar8.png)

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

원래는 이후 `http://127.0.0.1:4000/`에 들어가면 잘 되어야 하지만 나 같은 경우에는 `gemdecimal`이 없다는 오류가 떴다. `Gemfile`에 `gem 'bigdecimal', '1.4.2'`를 추가하고 하면 잘 된다.

### 내걸로 만들기

친절하게도 이 gihub.io는 Fork 후 뭘해야 할지 README.md 에서 알려준다. 하지만 그대로 하면 조금 잘 안 될 수 있다.

수정하면 다음과 같다.

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

## 글 포스팅 하기

기본적으로 나는 [HackMD](https://hackmd.io/)에서 마크다운을 작성하고 옮긴다. 또한 작성할때는 markdownlint를 사용하는데 MD013과 MD025, MD033만 사용하지 않는다.

### 포스팅 파일

파일 이름을 `yyyy-MM-dd-이름.md` 형식으로 해서 `_posts`폴더에 넣어주면 된다.

### YAML front matter

이 내용을 포스팅 최상단에 적어야 한다.

```yml
---
title: "제목"
date: yyyy-MM-dd HH:mm:ss
categories:
- 카테고리
tags:
- 태그1
- 태그2
- 태그3
---
```

- title은 포스팅 제목
- date는 포스팅 업로드 날짜
- categories는 포스팅 카테고리가 되고, 포스팅 링크가 되는 `블로그주소/카테고리/yyyy/MM/dd/이름/`에서 `카테고리` 부분에 나타나게 된다.
- tags는 포스팅에 달리는 태그가 된다. 이 블로그 테마의 경우 포스팅 하단에 태그가 표시되고, `블로그주소/tags/`에서 태그들을 모아 볼 수 있다.
