---
layout: post
title: "[MariaDB] 테이블 row 갯수, 사이즈 쿼리"
description:
tags: [dev]
author: hdmun
comments: true
---

~~~sql
SELECT 
    table_name,
    table_rows,
    round(data_length / (1024*1024), 2) as 'DATA_SIZE(MB)',
    round(index_length / (1024*1024), 2) as 'INDEX_SIZE(MB)'
FROM information_schema.TABLES
where table_schema = 'DB이름'
~~~
