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


# 개인키(Private Key) 생성
~~~cmd
openssl genrsa -aes256 -out webdav_private.key 2048
~~~

# 공개키(Publick Key) 생성
~~~cmd
openssl rsa -in webdav_private.key -pubout -out webdav_public.key
~~~

# CSR 생성
~~~cmd
openssl req -new -key webdav_private.key -out webdav_private.csr
~~~

# CRT 생성

## CA 키 생성
~~~cmd
openssl genrsa -aes256 -out webdav_rootCA.key 2048
~~~

## CA 키 CSR 생성
~~~cmd
openssl req -x509 -new -nodes -key webdav_rootCA.key -days 3650 -out webdav_rootCA.pem
~~~

## CRT 키 생성
~~~cmd
openssl x509 -req -in webdav_private.csr -CA webdav_rootCA.pem -CAkey webdav_rootCA.key -CAcreateserial -out webdav_private.crt -days 3650
~~~

# references

https://namjackson.tistory.com/24
https://www.lesstif.com/pages/viewpage.action?pageId=6979614

