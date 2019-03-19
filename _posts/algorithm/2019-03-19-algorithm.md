---
layout: post
title: 프로그래머스 level 1 -  문자열 내 p와 y의 개수
category: algorithm
permalink: /til/:year/:month/:day/:title/
tags: [algorithm]
comments: true
---


## **프로그래머스 level 1 -  문자열 내 p와 y의 개수**

#### [문제](https://programmers.co.kr/learn/courses/30/lessons/12916)


#### 180913 풀이 

```js
function solution(s){
    var answer = true;
    var ls = s.toLowerCase();
    var p = [...ls].filter(l => l ==='p').length
    var y = [...ls].filter(l => l ==='y').length
    console.log('p = '+p);
    console.log('y = '+y);
    if (p !== y){
        answer = false;
    }
    return answer;
}
```

- 굉장히 신박하게 풀었네...? 굳이 `filter`를... 

#### 190319 풀이 (5분 17초)

```js
function solution(s) {
    let pC = 0;
    let yC = 0;

    s.toLowerCase().split("").forEach((l) => {
        if (l === "p") pC++;
        else if (l === "y") yC++;
    })

    return pC === yC ? true : false
}
```

- 아 근데 저 분기문을 줄일 수 있는 방법이 있을 것 같은데.. 여전히 뭔가 awesome하지 않다..!! 구리다!!! 더 잘할 수 있는데!!

#### 요 풀이 좋다. 

```js
function numPY(s){
    return s.toUpperCase().split("P").length === s.toUpperCase().split("Y").length;
}
```

이런 코드 짜고 시펑.... 간지....ㅠㅠ 