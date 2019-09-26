---
layout: post
title: "비주얼 스튜디오 미리 컴파일된 헤더 만들기"
description: >
  Visual Stduio C++ 프로젝트에서 미리 컴파일된 헤더가 없을 때 만드는 방법에 대해 설명합니다.
tags: [devlog]
author: hdmun
comments: true+
---

`미리 컴파일된 헤더`는 비주얼 스튜디오에서 C++ 프로젝트 생성할 때 옵션으로 만들 수 있다. 하지만 만들지 않고 쓰다가 중간에 `미리 컴파일 된 헤더`를 추가해야 할 때도 있다.

`미리 컴파일된 헤더` 없이 프로젝트 생성 후 개발하다가 중간에 추가하는 방법을 정리하였다. 순서 상관 없이 아래 모든 항목을 따라하면 된다.

## 프로젝트 속성

구성 속성 - C/C++ - 미리 컴파일된 헤더로 가서 아래 스크린샷 처럼 `미리 컴파일 된 헤더` 옵션을 `사용(/Yu)`으로 설정한다. 프로젝트 구성, 플랫폼마다 일일이 해주기 귀찮으니 `모든 구성`, `모든 플랫폼`으로 바꿔놓고 설정해주자.

![add-vs-pre-complied-header-step_01]({{ "/assets/img/add-vs-pre-complied-header/step_01.jpg" }})

## stdafx.h, stdafx.cpp 파일 추가

stdafx.h, stdafx.cpp 파일을 생성해서 추가해주자

![add-vs-pre-complied-header-step_02]({{ "/assets/img/add-vs-pre-complied-header/step_02.jpg" }})

## stdafx.cpp 파일 속성

아래 스크린샷 처럼 `미리 컴파일 된 헤더` 옵션을 `만들기(/Yc)`로 설정한다. 프로젝트 구성, 플랫폼마다 일일이 해주기 귀찮으니 `모든 구성`, `모든 플랫폼`으로 바꿔놓고 설정해주자.

![add-vs-pre-complied-header-step_03]({{ "/assets/img/add-vs-pre-complied-header/step_03.jpg" }})

## 프로젝트 내 모든 cpp 파일 최상단에 #include "stdafx.h" 추가

![add-vs-pre-complied-header-step_04]({{ "/assets/img/add-vs-pre-complied-header/step_04.jpg" }})


위 설정을 다 했으면 이제 빌드 해보자 잘 될것이다.
