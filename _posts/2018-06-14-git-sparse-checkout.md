---
layout: post
title: "[git] 서브 디렉토리만 체크아웃 하기"
description: >
  git에서 서브 디렉토리만 체크아웃 하는 방법을 정리해보았다  
tags: [devlog]
author: hdmun
comments: true
---

sparse checkout 라는 기능이 있다.  
SVN 처럼 루트로 잡을 순 없지만  
이걸로 서브 디렉토리만 체크아웃 받을 수 있다.  

깃허브 페이지 프로젝트 내 **_js**폴더만 체크아웃 받아보자  

~~~batch

set PROJ=hungrysoul9.github.io
set REMOTE_URL=https://github.com/hungrysoul9/hungrysoul9.github.io.git

set CHECKOUT_PATH=_js/*

mkdir %PROJ%
cd %PROJ%

git init
git remote add -f origin %REMOTE_URL%

git config core.sparseCheckout true
echo %CHECKOUT_PATH%> .git/info/sparse-checkout

git pull origin master

pause
~~~
