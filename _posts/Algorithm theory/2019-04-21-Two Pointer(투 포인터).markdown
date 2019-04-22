---
layout: post
title:  "Two Pointer(투 포인터)"
date:   2019-04-21 00:14:54
categories: Algorithm Theory
comments: true
---

출처 : https://www.codeground.org/common/popCodegroundNote#  



투 포인터(Two Pointer) 알고리즘은 연속된 값들을 이용하여 풀어나가는 문제에 한정적으로 사용해야 하지만 매우 효율적인 알고리즘입니다.  

직관적으로 보았을 때 O(N^2)이상으로 해결해야하는 문제를 선형시간(O(N))으로 해결해주기 때문입니다.  

예를 들면, 1. 정렬된 두 배열이 주어질 때 두 배열을 하나의 정렬된 배열로 합치는 경우,  

2 . 어떤 배열의 연속 부분집합(contiguous subrarray)의 원소의 합이 k인 경우의 수를 찾는 경우 등이 있습니다.  

투 포인터 알고리즘의 기본 동작원리는 이름 그대로 두 개의 지점(포인터)를 옮겨가면서 구하고자 하는 답을 구하는 것입니다.  


1번에서 두 배열을 이어 정렬한다면 O((N+M)log(N+M))에 해결할 수 있지만,  

투 포인터를 사용할 경우 A배열의 포인터가 한번 순회, B배열의 포인터가 한번 순회로 총 O(N+M)이 나오므로 효율적입니다.  

2번에서 투 포인터를 사용하면  

>SUM[L,R] < k 일 때, R을 증가시켜주어 k에 근접할 수 있도록 범위를 넓혀주며  
SUM[L,R] > k 일 때, L을 증가시켜주어 범위를 좁혀주며  
SUM[L,R] == k 일 때는 정답을 카운트해주며 다음 경우를 찾기 위해 다시 L을 증가시켜주어 범위를 좁혀줍니다.  
이 알고리즘 또한 두 포인터가 하나의 배열을 두 번 탐색하는 것과 같으므로 시간복잡도는 O(N)으로 빠르게 동작합니다.  

특수한 상황에서만 적용 가능한 알고리즘이지만, 동작속도가 빠르므로 유용하게 쓰입니다.  

#### 1번. 정렬된 두 배열을 합칠 때 코드

**입력**  
첫 번째 줄에 배열 A의 원소의 개수가 주어지고  
두 번째 줄에 배열 A의 원소가 주어진다.  
세 번째 줄에 배열 B의 원소의 개수가 주어지고  
네 번째 줄에 배열 B의 원소가 주어진다.  
배열 A, B는 모두 오름차순으로 정렬되어있다.  

Sample Input  	
4  
1  2  8  9  
5  
-3  3  4  5  11  

**출력**  
A, B 두 배열을 합친 후 원소들을 정렬하여 출력한다.  

Sample Output  
-3  1  2  3  4  5  8  9  11  

~~~cpp
#include <iostream>
#define MAX 5005
int A[MAX], B[MAX];
int Sorted[MAX + MAX];
int main() {
    int n, m;
    scanf_s("%d", &n);
    for (int i = 0; i < n; i++)
        scanf_s("%d", &A[i]);
    scanf_s("%d", &m);
    for (int i = 0; i < m; i++)
        scanf_s("%d", &B[i]);

    int a = 0, b = 0;//a와 b의 위치

    for (int i = 0; i < n + m; i++) {//★★★★★
        if (b == m || (b != m && a < n && A[a] < B[b]))
            Sorted[i] = A[a++];
        else
            Sorted[i] = B[b++];
    }

    for (int i = 0; i < n + m; i++)
        printf("%d ", Sorted[i]);
}
~~~
