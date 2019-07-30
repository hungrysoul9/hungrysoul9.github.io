---
layout: post
title: "[Pokemon Go] 포켓몬 고 iSpoofer Cydia Impactor로 설치하는 방법"
description: >
  
tags: [PokemonGo]
author: hdmun
comments: true
---

포켓몬 고 GPS 조작이 가능한 iSpoofer 어플을 시디아 임팩터(Cydia Impactor)로 설치하는 방법에 대한 포스팅입니다.

작성 기준은 윈도우 PC 기준입니다.



## 준비 과정

설치에 앞서 몇 가지 다운로드가 필요합니다. 순서대로 설명하겠습니다.


### Pokemon GO 어플 삭제

Pokemon GO 어플이 설치되어 있다면 삭제를 하셔야 설치가 됩니다. 삭제해주세요.


### 아이튠즈 설치

아이튠즈가 PC에 설치되어 있어야 합니다. 애플 홈페이지가셔서 다운로드 받으시거나, 윈도우 10이라면 `마이크로소프트 스토어`에서 아이튠즈를 다운받아 설치합니다.


### Cydia Impactor 다운로드

이제 Cydia Impactor를 다운로드 받습니다. [Cydia Impactor 다운로드 링크](https://cydia.saurik.com/api/latest/2)

다운로드 받으시면 zip 파일로 되어있는데 압축을 미리 풀어놓습니다.

![pogo_cydiaimpactor_prepare_01]({{ "/assets/img/pokemongo/pogo_cydiaimpactor_prepare_01.jpg" }})


### IPA 다운로드

iSpoofer 어플 파일인 IPA 파일 다운로드가 필요합니다. iSpoofer 홈페이지에서 IPA 파일을 다운로드 받습니다.

https://www.ispoofer.com/ispoofer-for-pogo/

![pogo_cydiaimpactor_prepare_02]({{ "/assets/img/pokemongo/pogo_cydiaimpactor_prepare_02.jpg" }})

[IPA 직접 다운로드 링크](https://www.ispoofer.com/redir/dl/pmgo4)

![pogo_cydiaimpactor_prepare_03]({{ "/assets/img/pokemongo/pogo_cydiaimpactor_prepare_03.jpg" }})



## 설치 시작

자, 이제 설치를 시작해봅시다.


### Cydia Impactor 실행

앞서 다운로드 받았던 Cydia Impactor를 실행하고, 아이폰을 PC와 연결합니다. 그리고 다운로드 받았던 `ipa` 파일을 Cydia Impactor로 마우스로 드래그앤드랍을 합니다.

![pogo_cydiaimpactor_01]({{ "/assets/img/pokemongo/pogo_cydiaimpactor_01.jpg" }})

그러면 아래와 같은 화면이 뜨는데요, 자신이 사용하고 있는 애플 아이디를 입력합니다.

![pogo_cydiaimpactor_02]({{ "/assets/img/pokemongo/pogo_cydiaimpactor_02.jpg" }})

애플 아이디 암호를 입력하면 설치를 시작합니다.

![pogo_cydiaimpactor_03]({{ "/assets/img/pokemongo/pogo_cydiaimpactor_03.jpg" }})

Complete 가 뜨면 설치 완료

![pogo_cydiaimpactor_04]({{ "/assets/img/pokemongo/pogo_cydiaimpactor_04.jpg" }})


### 오류 메세지 발생

최신 iOS를 사용 중이시면 대부분 아래와 같은 오류 메세지가 발생하실 겁니다.

![pogo_cydiaimpactor_05]({{ "/assets/img/pokemongo/pogo_cydiaimpactor_05.jpg" }})

애플 아이디 `이중 인증`이 켜져 있어서 발생하는 문제인데요. `이중 인증`은 한 번 켜지면 끌 수가 없으므로 별도의 앱 설치용 암호를 발급 받아서 다시 설치를 진행하셔야 합니다.

`이중 인증`이 켜져 있는지 부터 확인한 후에 앱 설치용 암호를 발급 받는 방법을 알아보겠습니다.


### 아이폰 이중 인증 여부 확인

1. 아이폰 설정 앱으로 이동합니다.
2. `사용자 이름`으로 이동합니다.
3. `암호 및 보안`으로 이동합니다.
4. 이중 인증이 켜져 있는지 확인합니다.

![pogo_cydiaimpactor_iphone_01]({{ "/assets/img/pokemongo/pogo_cydiaimpactor_iphone_01.jpg" }})
![pogo_cydiaimpactor_iphone_02]({{ "/assets/img/pokemongo/pogo_cydiaimpactor_iphone_02.jpg" }})
![pogo_cydiaimpactor_iphone_03]({{ "/assets/img/pokemongo/pogo_cydiaimpactor_iphone_03.jpg" }})


### 앱 설치용 암호 키 발급

https://appleid.apple.com/ 홈페이지로 이동해서 애플 아이디로 로그인을 합니다.

로그인 후 `보안` 항목에 보시면 `앱 암호` - `암호 생성...`을 클릭해줍니다.

![pogo_cydiaimpactor_apple_key_01]({{ "/assets/img/pokemongo/pogo_cydiaimpactor_apple_key_01.jpg" }})

그러면 팝업 창이 하나 뜨는데요 `암호 레이블`란에 아무거나 입력합니다. (저는 '시디아 임팩터 설치용'으로 했습니다.)

![pogo_cydiaimpactor_apple_key_02]({{ "/assets/img/pokemongo/pogo_cydiaimpactor_apple_key_02.jpg" }})

`생성` 버튼을 누르시면 키가 생성이 되는데요 '-'를 포함한 키 값 전체를 편하신 방법으로 저장해놓습니다. (저는 카톡으로 보내놨었습니다.)

![pogo_cydiaimpactor_apple_key_03]({{ "/assets/img/pokemongo/pogo_cydiaimpactor_apple_key_03.jpg" }})

다시 Cydia Impactor로 가셔서 동일하게 설치를 진행하시는데 암호 입력할 때 위에서 발급 받은 키 값을 입력하시면 설치가 됩니다.


## 설치 완료

이제 설치가 완료되었으면 마지막 단계가 남아있습니다.

### 앱 신뢰 설정

아이폰 `설정` - `일반` - `프로파일 및 기기 관리`로 들어갑니다.

설치했을 때 입력했던 애플 아이디가 보일겁니다. 탭해서 들어가 줍니다.

![pogo_cydiaimpactor_done_01]({{ "/assets/img/pokemongo/pogo_cydiaimpactor_done_01.jpg" }})

'어쩌구 저쩌구~~ 신뢰함' 버튼 탭

![pogo_cydiaimpactor_done_02]({{ "/assets/img/pokemongo/pogo_cydiaimpactor_done_02.jpg" }})

'신뢰' 버튼 탭

![pogo_cydiaimpactor_done_03]({{ "/assets/img/pokemongo/pogo_cydiaimpactor_done_03.jpg" }})


# 끝났습니다. 실행하셔서 마음껏 뛰어다니세요
