---
layout: post
title: "[git] push 되돌리기"
description: >
tags: [devlog]
author: hdmun
comments: true
---

개인 프로젝트에 git-flow를 사용하고있다.  
의도하지 않게 master에 develop의 내용들을 rebase 후 push를 했었는데  

찾아보니 원격 저장소에 push 되어있는 커밋 목록들을 날리는 방법이 있더라  
기록해두자  

~~~batch
git reset [커밋ID]
git push origin +master
~~~

자세한 내용은 아래에서  

{:message}
  > **references**
  1. [git commit & push 된거 강제 rollback 하기(원격저장소 원복)](http://papababo.tistory.com/213)  
  2. [[Git] 아흑.. 커밋을 잘못했네;; 세상에 푸쉬까지 해버렸는데… 어쩌지… ](http://whiteship.me/?p=13516)  
