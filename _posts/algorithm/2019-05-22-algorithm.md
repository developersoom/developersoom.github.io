---
layout: post
title: 소수 구하기 - 에라토스테네스의 체
category: algorithm
permalink: /til/:year/:month/:day/:title/
tags: [algorithm]
comments: true
---


## **소수 구하기 - 에라토스테네스의 체**

#### [문제](https://www.acmicpc.net/problem/1929)

#### 이해가 계속 안 갔던 에라토스테네스의 체를 뽀개보기로 했다.

### 원리

![image](https://upload.wikimedia.org/wikipedia/commons/b/b9/Sieve_of_Eratosthenes_animation.gif) [wikipedia]

너무나 잘 알고 있고, 이해가 되는 그림인데 코드로 구현을 못했었다. 

어제는 최솟값~최댓값까지 숫자를 배열에 다 push해놓고, 루프를 돌면서 지우는 방식으로 구현해보려고 했는데, 영 구현이 안됐다. 

while 탈출문도 뭐로 해야될 지 모르겠었고...

30분 고민하고 못풀면 답을 보라는 조언을 또 무시한채 2시간 붙잡고 있다가, 인터넷에서 코드를 참고했다.

```javascript
function getPrime(min, n) {
    let upperLimit = Math.sqrt(n);
    let output = [];
    let array = Array(n).fill(true);

    for (let i = min; i <= upperLimit; i++) {
        if (array[i]) {
            for (let j = i * i; j < n; j += i) {
                array[j] = false;
            }
        }
    }

    for (let i = min; i < n; i++) {
        if (array[i]) {
            output.push(i);
        }
    }

    return output;
}
```

```js
let array = Array(n).fill(true);
```
여기서 최댓값만큼 `true`로 배열을 채워두고,
![image](https://user-images.githubusercontent.com/40848630/58300697-98d93080-7e1e-11e9-99f0-14cd4b8cbba8.png)

```js
for (let i = min; i <= upperLimit; i++) {
    if (array[i]) {
        for (let j = i * i; j < n; j += i) {
            array[j] = false;
        }
    }
}
```

배열을 돌면서 소수를 찾고, 해당 배수를 `false`로 바꿔주는 것이다.

다른 부분은 코드를 보고 이해가 됐는데, upperLimit 부분이 이해가 안갔다.
![image](https://user-images.githubusercontent.com/40848630/58300964-a347fa00-7e1f-11e9-8632-e7ac4754617b.png)
나무위키에서 이런 글을 봤는데, 더 이해가 안갔...  
공대 친구들한테 물어봤는데 `깊게 생각하지 마라`는 답변을...


그래서 차근차근 생각해봤는데,

`n~m사이의 어떤 수는 제곱근m 배수 이상의 수로 나눠지지 않기 때문`인 것 같다.

그니까 1부터 100까지 수가 있다면, 10의 배수인 100은 이미 100이니까? 10이하의 수만 체크해보면 된다... 그런 느낌적인 느낌인듯...