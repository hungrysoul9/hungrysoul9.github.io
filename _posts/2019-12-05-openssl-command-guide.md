---
layout: post
title: "[OpenSSL] 인증서 생성하기"
description: >
  
tags: [dev]
author: hdmun
comments: true
---

개인 WebDAV 서버에 HTTPS 적용을 위해 OpenSSL 인증서를 적용하였다.

언제 또 까먹을지 모르니 인증서 생성 과정을 정리해놓자.

커맨드만 있으므로 주의

# CRT 생성

## CA 키 생성
~~~cmd
openssl genrsa -aes256 -out webdav-rootca.key 2048
~~~

## CA 키 CSR 생성
~~~cmd
openssl req -new -key webdav-rootca.key -out webdav-rootca.csr -config webdav_rootca_openssl.conf
~~~

## CRT 키 생성
~~~cmd
openssl x509 -req -days 3650 -extensions v3_ca -set_serial 1 -in webdav-rootca.csr -signkey webdav-rootca.key -out webdav-rootca.crt -extfile webdav_rootca_openssl.conf
~~~


# 개인키(Private Key) 생성
~~~cmd
openssl genrsa -aes256 -out webdav-private.key.enc 2048
~~~

## 개인키(Private Key) pass phrase 제거
~~~cmd
openssl rsa -in webdav-private.key.enc -out webdav-private.key
~~~

# SSL 인증서 요청 생성
~~~cmd
openssl req -new -key webdav-private.key -out webdav-host.csr -config webdav_host_openssl.conf
~~~

# SSL 인증서 발급
~~~cmd
openssl x509 -req -days 1825 -extensions v3_user ^
-in webdav-host.csr ^
-CA webdav-rootca.crt ^
-CAcreateserial ^
-CAkey webdav-rootca.key ^
-out webdav-host.crt ^
-extfile webdav_host_openssl.conf
~~~

# IIS 인증서 등록을 위한 pfx 파일 만들기

~~~cmd
openssl pkcs12 -export -in webdav-host.crt -inkey webdav-host.key -out webdav-host.pfx
~~~


# references

https://namjackson.tistory.com/24
https://www.lesstif.com/pages/viewpage.action?pageId=6979614

