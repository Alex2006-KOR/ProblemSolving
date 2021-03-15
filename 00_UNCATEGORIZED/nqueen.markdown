---
layout: post
title: 1-1 Example N-Queen
date: 2021-03-15 13:25:20 +0300
author: Alex2006
---
  
  
------
## 1. N-Queen
![QUEEN1](./img/queen_1.jpg)
  * Problem - N x N 체스 보드 위에 1행 마다 1개씩 N개의 말을 놓는데, 각 말에서 Queen 이동범위 내에 다른 말이 없도록 한다.
 


## 2. Recursive(Backtracking) Thinking
![QUEEN2](./img/queen_2.jpg)
  * 3번째 행에 말을 놓을 수 없으므로 가장 최근 결정인 2행을 변경
![QUEEN3](./img/queen_3.jpg)
  * 4번째 행에 말을 놓을 수 없으므로 가장 최근 결정인 3행을 변경
     --> 2번째 취소 --> 1번째 취소
![QUEEN4](./img/queen_4.jpg)
  * N-Queen 완성

  * 각 선택에서 결정을 내리며 진행하다가 막히게 되면 가장 최근의 결정부터 새로운 선택을 시도/반복
     --> 상태 공간 트리로 표현이 가능
![QUEEN5](./img/queen_5.jpg)
  * non-promising / infeasible : 모든 노드를 탐색하지 않아도 답을 구 할 수 있다.



## 2. Pseudo Code(Recursion Design)
```cpp
return_type Queens (Arguments) //
{
    if non-promising
        report failure or return FALSE // 조건에 맞지 않는 노드라면
    else if success
        report answer or return TRUE // 이 노드가(도달한) 정답이라면
    else
        visit child recursively                 // recursive 하게 자식 방문
}
```



## 3. Implemantation

```cpp
// Global variable : Chess board
int [] cols = new int[N+1]
```
```cpp
boolean  Queens (int level) // Arguments : level => cols[level] == level 행에 놓인 말 위치
    if (!Promising(level))
        return FALSE
    else if  (level == N)
        return TRUE

    for (int i = 1; i <= N; i++)
        cols[level+1] = i
        if (Queens(level + 1))
            return TRUE

    return FALSE
```
```cpp
boolean  promising (int level)
    for (int i = 1; i < level; i++)
        if (cols[i] == cols[level])
            return FALSE
        else if (level-i == |cols[level] - cols[i]|)
            return FALSE

    return TRUE
```


## 4. Problem
  * TBD

------