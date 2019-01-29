---
layout: post
title:  "jekyll-Github연동-및-테마-적용하기"
date:   2019-01-29 21:14:54
categories: jekyll
comments: true
---

## Jekyll Github와 연동하기

### 1. Github에 Repository 생성

레포 생성 시 Repository name을 `자신의Github아이디.Github.io` 로 생성해준다.

### 2. Git과 연동하기

`$git init`

`$git add .`

`$git commit -m "Commit mesaage`

`$git remote add origin "자신의 Git URL주소 ex)https://github.com/asdasd/asdasd.github.io.git"` (해당 Repositrot에서 Clone or download를 클릭하면 볼 수 있다.)

`$git push origin`

### 3. 확인하기

* http://자신의Github아이디.github.io

를 입력하여 잘 되었는지 확인한다.

## Jekyll 테마 적용하기

### 1. Jekyll 테마 다운하기

http://jekyllthems.org/

해당 사이트에 접속하여 마음에 드는 테마를 찾는다. (간혹 불량한 테마도 있으니 잘 찾아보아야한다.)
테마를 찾은 후 download를 클릭하여 테마를 download한다.

### 2. 다운 받은 테마 적용하기

다운받은 테마의 압축을 푼 후, 자신의 Jekyll 디렉토리안에 넣어준다.
넣은 후 위에서 2번을 다시 반복해주면 자신의 테마가 바뀌었음을 확인할 수 있다.
또는 `jekyll s`를 통해 바로 확인할 수 있다. <- 방법은 [jekyll 설치 및 준비하기](https://chogyujin.github.io/2019/01/28/jekyll-%EC%84%A4%EC%B9%98-%EB%B0%8F-%EC%A4%80%EB%B9%84%ED%95%98%EA%B8%B0/)를 참고하면 된다.

이후부턴 `$git init`과 `git remote add origin ~~`는 생략가능 하다.
