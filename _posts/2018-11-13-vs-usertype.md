---
layout: post
title: "[VisualStudio] 텍스트 편집기에서 특정 키워드 색 지정하기"
description: >
  특정 키워드 색 지정하기
tags: [devlog]
author: hdmun
comments: true
---

락 관련 키워드를 빨갛게 표시해서 동기화 처리에 주의하고 싶었다  

텍스트 포맷의 USERTYPE.DAT 파일을 만들어서  
devenv.exe 파일과 동일한 경로에 두자  

~~~
ZLock
m_lock
GetLock()
need_lock
auto_lock
auto_lock_ex
auto_unlock_ex
synchronized
synchronized_ex
ignore_lock_order
~~~

도구 - 옵션 
환경 - 글꼴 및 색 - 표시항목 - C/C++ 사용자 키워드
