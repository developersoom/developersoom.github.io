---
layout: post
title: 프로그래머스 level 1 -  수박수박수박수박수박수?
category: algorithm
permalink: /til/:year/:month/:day/:title/
tags: [algorithm]
comments: true
---


## **프로그래머스 level 1 -  수박수박수박수박수박수?**

#### [문제](https://programmers.co.kr/learn/courses/30/lessons/12922)

#### 180913 풀이 

```js
function solution(n) {
    var answer = '';
    var arr = [];

    for (let i = 0; i < n; i++) {
        if (i === 0 || i % 2 === 0) {
            arr.push('수');
        } else {
            arr.push('박');
        } answer = arr.toString();
        answer = arr.join("");          
    }
    console.log(answer);
    return answer;
}
```

- 이땐 무조건 array를 써서 푸는 방법밖에 몰랐던 것 같다. 
- `console.log()`는 왜 놔둔채로...


#### 190315 풀이 (4분 30초)

```js
function solution(n) {
    let answer = "";
    for(let i = 0; i < n; i++) {
        i % 2 ? answer += "박" : answer += "수"
    }
    return answer;
}
```

- 좀 더 간결해진 느낌! 


````
알고리즘 풀때마다 바로 코드부터 짜지 말고 펜을 들고 설계하라는 말씀을 실천하려고 한다!

여러 문제를 많이 푸는 것보다, 시간을 재고 같은 문제를 여러번 푸는 것이 도움이 된다고 해서, 앞으로 예전에 풀었던 알고리즘 문제를 15분 시간 제한을 두고 다시 풀어볼 계획이다!
````