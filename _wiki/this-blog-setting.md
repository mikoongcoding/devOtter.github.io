---
layout  : wiki
title   : 
summary : 
date    : 2022-01-17 23:11:22 +0900
updated : 2022-03-27 00:01:59 +0900
tags    : 
toc     : true
public  : true
parent  : 
latex   : false
---
* TOC
{:toc}

## utterances 댓글 세팅
- _config.yml
- _includes/comment.html
- utterances.json

## random 버튼
- wikiindex.html > random()
- header.html

## vimwiki md 파일 설정..

```
" let g:vimwiki_global_ext = 0
```

주석처리 했다.

이유는 터미널에서 nvim을 치고 startify 화면이 나오는데 `\ww` 단축키로 들어가면 vimwiki로 인식된 index.md가 나오고, startify 에서 경로로 표시되어 있는 index.md를 들어가면 vimwiki를 사용할 수 없다. 그래서 주석처리했더니 이제 두 경우 모두 vimwiki로 사용할 수 있다.

## git hooks

내 .git/hooks 폴더에 pre-commit 파일이 활성화 안되어 있음을 이제 알았다

그런데 이런 메세지가 떴다..
>
hint: The '.git/hooks/pre-commit' hook was ignored because it's not set as executable.
hint: You can disable this warning with `git config advice.ignoredHook false`.
>

```
chmod ug+x .git/hooks/*
```

이 명령어를 실행했는데 이후로 안뜬다 그럼 훅이 제대로 실행된걸까?

tool 폴더에 있는 pre-commit 파일을 그대로 갖다붙여넣었다.. 이번에는 될까?

>
env: node: No such file or directory
_wiki/this-blog-setting.md
./tool/save-images.sh: line 16: ag: command not found
Success: 0, Fail: 0
fatal: pathspec '_data' did not match any files
[main 6ae8f66] 글 작성
 2 files changed, 3 insertions(+), 1 deletion(-)
>

오 훅 돌았다! 돈것이 확실! 이제 저런.. 에러ㄴ들 처리하면 되겠다

기계인간님 깃헙에서 최신 save-images.sh 파일을 가져와서 붙여넣었다.

## data/total-document-url-list.json 파일을 생성

자동으로 json 파일이 만들어지는 것 같지 않아서 data 폴더에 mkdir 명령어로 파일을 생성했다. 이제 generateData.js가 돌면서 data/total-document-url-list.json파일에 내 문서목록을 적어주는 걸까?

아이고 이건 폴더 만드는 명령어 였구나. vim 으로 파일 생성했다 공백줄을 추가하여..

## the silver searcher a.k.a Ag
```
ag command not found
```

`git commit`할 때 이런 메세지가 떠서 `brew install the-silver-searcher`로 설치했더니 더이상 안뜬다.
## Node & NPM 설치

```
env: node: No such file or directory
```

위키에 글을 쓰고 `git commit`을 하면 위와 같은 메세지가 낑겨있었다.
`brew install node`로 Node.js를 설치했다.

잘 설치되었는지 확인은 아래 명령어로 terminal에서 확인한다.
```
$ node -v

$ npm -v
```

### yamljs module 설치
```
node:internal/modules/cjs/loader:936
  throw err;
  ^

Error: Cannot find module 'yamljs'
```

node를 설치하고 git commit 을 했더니(git commit에서 계속 걸리는 이유는 pre-commit이 도는데 거기에 generateData.js가 있고 이 js에서..yamljs랑 f..뭐시기가 있다.

아무튼 이번 에러는 yamljs를 설치하면 될 것 같다.

>
Use with node.js
>
Install module:
npm istall yamljs

Use it:
YAML = require('yamljs');
>

`fs`라는 모듈도 generateData.js에서 yamljs처럼 쓰고 있으니, npm install fs도 실행해보자.


