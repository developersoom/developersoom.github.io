---
layout: post
title: 프로그래머스 level 1 -  자릿수 더하기
category: algorithm
permalink: /til/:year/:month/:day/:title/
tags: [algorithm]
comments: true
---


## **프로그래머스 level 1 -  자릿수 더하기**

#### [문제](https://programmers.co.kr/learn/courses/30/lessons/12931?language=javascript)

#### 180914 풀이 

```js
function solution(n) {
    var answer = 0;
    var number = n.toString();
    var value = number.split("");
    
    value.forEach(function(v,i,a){
        answer += Number(a[i]);
    });

    console.log(answer);
    return answer;
}
```

- console은 그냥 매번 찍어서 제출했나보다..ㅋㅋ
- 굳이 변수에 각각 선언해서 메모리를 아주 잘 낭비했다. 
- `forEach`가 적합한 메소드인 것 같지 않다. 

#### 190321 풀이 (5분 27초)

```js
function solution(n) {
    return n.toString().split('').reduce((a,b) => Number(a)+Number(b), 0)
}
```

- 예전 풀이랑 크게 차이는 없는듯... 한 줄에 끝냈다는 거 외에는.. 
- 초기값 0을 안줬더니 마지막 테스트코드에서 실패했다. 
- 효율성은 별로 안 좋은 것 같다.
- 다른 사람 풀이도 근데 비슷비슷하다. 