---
layout: post
title: 1-1 Example Counting cells in a blob
date: 2021-03-09 13:25:20 +0300
author: Alex2006
---
  
  
------
## 1. Counting cells in a blob
![BLOB](./img/blob.jpg)
  * 입력  - N * N 크기의 이차원 Grid, 하나의 좌표(x, y)
  * 출력 - 픽셀(x, y)가 포함된 blob의 크기, 픽셀이 어떠한 blob에도 속하지 않으면 0


## 2. Recursive Thinking
#### * 현재 픽셀이 image color가 아니라면 return 0
#### * 현재 픽셀이 image color라면
#####     1) 먼저 현재 픽셀을 카운트 한다.
#####     2) 현재 픽셀에 대한 중복 카운트를 방지하기 위해 다른 색으로 칠한다.
#####     3) 현재 픽셀에 이웃한 8개 픽셀들에 대해 <span style="color:red">그 픽셀이 속한 blob의 크기를 카운트 하여 카운터에 더한다.</span>



## 3. Pesudo Code
#### * Step1

```cpp
bool findPath(x, y)
    if (x, y) is the exit then
        return TRUE
    else
        foreach neighboring cell (x', y') of (x, y) do
            if (x', y') is on the pathway
                if findPath (x', y') then
                   return TRUE
    return FALSE
```
 * 두가지가 결여되어 있다 (1)  Basecase, (2) Basecase로의 수렴

#### * Step2

```cpp
bool findPath(x, y)
    if (x, y) is either on the wall or visited cell then
        return FALSE
    else if (x, y)is exit then
        ... ...
    else
        mark(x, y) as a visited cell
        foreach neighboring cell (x', y') of (x, y) do
        ... ...
```

## 4. Problem
#### * [미로탈출 14923](https://www.acpcmicpc.net/problem/14923)

#### * Reference code

------