---
title: Sapper, Github page, 그리고 Blog. 👋
date: "2020-02-10T21:16:00.000Z"
---

# Hello, sapper!
깃허브 페이지로 블로그를 하나 만들고 싶었는데 선택지가 많았다. Jekyll, Hexo, Hugo... 하루종일 삽질하다가 굳이 Jekyll을 사용하는 이유를 도무지 찾지 못해서 Hexo를 찾아 또 다시 삽질을 시작했다. Hexo에는 이쁜 스킨이 꽤 많았지만, 맘에드는 스킨은 대부분 중국어로 작성되어있었다. 환장할 노릇이다. 그러다가 어찌어찌 Svelte도 공부할 겸, Sapper를 사용해보기로 했다.

Sapper를 설치하고 npm run dev를 돌려보니 짜잔, 쌍따봉을 하고 있는 보랏이 보인다! 와, 이제 마크다운 파일을 읽고, 뿌려주는 녀석을 찾고... 하려니 역시 귀찮다. Jekyll이나 Hugo처럼 뭔가 없을까.

# 블로그 템플릿이 있어?
[Charca/sapper-blog-template](https://github.com/Charca/sapper-blog-template) 깃허브 브랜치에 블로그 용 Sapper 템플릿을 발견했다! 깃허브 페이지의 Getting started에 나와있듯이 설치 후 실행시켜보면, Sapper의 기본 템플릿과 굉장히 비슷한 페이지를 볼 수 있다. 그렇다, 쌍따봉을 날리고 있는 보랏 아조씨가 [unDraw](https://undraw.co/)의 이미지로 바뀌었다. 설치가 귀찮다면 [데모 페이지](https://sapper-blog-template.netlify.com/)를 확인해보자.

# 블로그 템플릿은 뭐가 달라?
[Charca/sapper-blog-template](https://github.com/Charca/sapper-blog-template) 깃허브 브랜치의 Structure항목을 보면 알 수 있지만, 간단하게 설명하면 마크다운 파일을 파싱하여 페이지로 만들어주는 녀석들이 추가됐다. 모자란 영어실력으로 간단하게 번역해봤다.

### src/routes/blog
* `_posts.js`: 이 모듈에는 마크다운으로 작성된 포스트를 파싱하고, 로딩하는 로직이 담겨있다.
* `[slug].svelte`: 블로그 포스트 페이지의 템플릿이다.
* `index.svelte`: 게시물 리스트 페이지의 템플릿이다. 

### src/routes/blog/posts
마크다운으로 작성된 포스트들이 위치한 경로다. 이 디렉토리에 위치한 `.md`파일들은 `_posts.js` 모듈에 의해 자동적으로 파싱되며, 블로그 포스트로 처리된다. 영어가 짧아서 이해가 안가는 구문은 (?)를 붙였다.
* 마크다운 파일은 포스트 슬러그가 된다.(?) 예를 들어 `hello-world.md`는 `http://localhost:3000/blog/hello-world`가 된다.
* 포스트의 시작과 `<!-- more -->` 태그 사이에 오는 모든 내용은 게시물의 '발췌'가 된다.(?)
* Frontmatter 속성은 `title`과 `date`를 지원한다.

구조를 조금 살펴보면 알겠지만, `src/components`의 내용을 수정하면 간단하게 포스트의 레이아웃을 변경할 수 있다. 와! 간단해라! ' ㅂ'!

다음에는 discus를 이용해서 댓글을 다는 법에 대해 알아보자.