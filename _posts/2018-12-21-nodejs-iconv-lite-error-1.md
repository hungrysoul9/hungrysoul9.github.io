---
layout: post
title: "[Nodejs] iconv-lite electron, webpack 관련 에러 해결"
description:
tags: [devlog]
author: hdmun
comments: true
---

일렉트론, vue를 사용해 팀 내부 툴을 만드는 중에  
한글 인코딩 관련 처리를 할 일이 생겼다.  

iconv-lite를 사용하는 중에 에러를 해결한 방법을 공유한다.  


## iconv-lite Error 에러
electron-vue 모듈을 사용해서 개발 중인데 iconv-lite 모듈 설치 후 실행하면  
아래 두 가지 에러가 발생한다.  


### require 사용 했을 때
~~~js
let iconv = require('iconv-lite')
~~~

>WARNING in configuration
The 'mode' option has not been set, webpack will fallback to 'production' for this value. Set 'mode' option to 'development' or 'production' to enable defaults for each environment.
You can also set it to 'none' to disable any default behavior. Learn more: https://webpack.js.org/concepts/mode/

>ERROR in ./node_modules/iconv-lite/lib/index.js
Module not found: Error: Can't resolve './c' in 'D:\Github_hungrysoul9\workspace\WzDebugLauncher\node_modules\iconv-lite\lib'
 @ ./node_modules/iconv-lite/lib/index.js 144:8-22
 @ ./src/renderer/controller/imgconfig.js
 @ ./src/renderer sync ^\.\/(?!main(\.js)?$)
 @ ./test/unit/index.js


### import 사용 했을 때
~~~js
import iconv from 'iconv-lite'
~~~

> Electron 2.0.15 (Node 8.9.3) ERROR
{
"message": "Uncaught TypeError: r(...) is not a function\nat webpack:///node_modules/iconv-lite/lib/index.js:144:27 <- index.js:7:1098667\n\nundefined",
"str": "Uncaught TypeError: r(...) is not a function\nat webpack:///node_modules/iconv-lite/lib/index.js:144:27 <- index.js:7:1098667\n\nundefined"
}

### 해결
https://github.com/ashtuchkin/iconv-lite/issues/204  

**iconv-lite Github Issue** 페이지에서 위 이슈를 찾았다.  

webpack 설정 파일에 아래와 같이 추가하니 실행이 잘 된다.  

~~~js
module: {
  rules: [
    {
      test: /node_modules[\/\\](iconv-lite)[\/\\].+/,
      resolve: {
      aliasFields: ['main']
    }
  ]
}
~~~

글을 읽어보니 webpack과 관련된 문제인거 같은데  
일단 잘 되니까 더 이상 원인은 찾질 않았다.  
