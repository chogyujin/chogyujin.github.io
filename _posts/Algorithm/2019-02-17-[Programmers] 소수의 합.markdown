---
layout: post
title:  "[Programmers] 소수의 합"
date:   2019-02-17 22:30:54
categories: Algorithm
comments: true
---

https://programmers.co.kr/learn/courses/30/lessons/14406  

에라토스테네스의 체를 이용하여 풀었습니다.  

https://ko.wikipedia.org/wiki/%EC%97%90%EB%9D%BC%ED%86%A0%EC%8A%A4%ED%85%8C%EB%84%A4%EC%8A%A4%EC%9D%98_%EC%B2%B4  

에라토스테네스의 체는 소수를 구하기위한 간단한 방법으로  

이 방법을 적용하여 코딩을 하면 해당 문제를 시간초과 없이 풀 수 있습니다.  


~~~
#include <vector>
using namespace std;
 
long long solution(int N) {
    long long answer = 0;
    vector <bool> ch(N+1,true);//처음엔 모두 소수라고 표시
    for(int i = 2; i <= N; i++){
        if(ch[i]==true) answer += i;//해당 값이 true(소수)인경우 더해준다
        for(int j=i;j<=N;j+=i){//i번째부터 N까지 i의 배수 모두를 false로 바꿔준다
            ch[j] = false;
        }
    }
    return answer;
}
~~~

- **혼잣말**

결국 혼자 힘으로 풀지 못했다..  

테스트는 모두 맞았지만 효용성에서 시간초과를 해결하지 못해서 다른 사람의 코드를 보았고,  

그러다가 에라토스테네스의 체를 발견했다.  

이런 걸 몰랐다면 개고생해서 풀었을 것 같다.  

