---
layout: post
title:  "우분투(Ubuntu)에서 Timezone 간단하게 변경하기"
date:   2019-02-27 09:16:54
categories: Ubuntu
comments: true
---

### 우분투 시간 변경하기

#### * 시간 확인  


`$ date`를 통해 현재시간을 확인할 수 있습니다.  


#### * Timezone 변경하기

1. `$ cd /usr/share/zoneinfo/`에 들어가서 원하는 국가들을 보고 그 경로를 기억(복사)해 두세요.  

2. `$ sudo ln -sf /usr/share/zoneinfo/Asia/Seoul /etc/localtime`을 통해 우분투의 시간을 서울로 변경했습니다.  

다시`$ date`를 통해 시간을 확인해보세요.  


