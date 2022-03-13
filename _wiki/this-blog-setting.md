---
layout  : wiki
title   : 
summary : 
date    : 2022-01-17 23:11:22 +0900
updated : 2022-03-13 21:59:38 +0900
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
