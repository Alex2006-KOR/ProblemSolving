---
layout: post
title: 1-1 Example Counting cells in a blob
date: 2021-03-09 13:25:20 +0300
author: Alex2006
---
  
  
------
## 1. Counting cells in a blob
![BLOB1](./img/blob_1.jpg)
  * Binary image에 대해 각 픽셀은 background color이거나 image color이다.
  * 서로 연결된 image 픽셀들의 집합을 Blob이라고 하며 상하좌우 및 대각방향으로도 연결된 경우도 Blob에 해당   
![BLOB2](./img/blob_2.jpg)
  * 입력  - N * N 크기의 이차원 Grid, 하나의 좌표(x, y)
  * 출력 - 픽셀(x, y)가 포함된 blob의 크기, 픽셀이 어떠한 blob에도 속하지 않으면 0


## 2. Recursive Thinking
  * 현재 픽셀이 image color가 아니라면 return 0
  * 현재 픽셀이 image color라면   
    * 먼저 현재 픽셀을 카운트 한다.   
	* 현재 픽셀에 대한 중복 카운트를 방지하기 위해 다른 색으로 칠한다.   
	* 현재 픽셀에 이웃한 8개 픽셀들에 대해 <span style="color:red">그 픽셀이 속한 blob의 크기를 카운트 하여 카운터에 더한다.</span>



## 3. Pesudo Code

```cpp
algorithm_for_counting_blob(x, y)
    if the pixel(x, y) is outside the grid then the result is 0
    else if pixel(x, y) is not an image pixel or already counted then the result is 0
    else
        set the color of the pixel(x, y) to a red color
       the result is 1 plus the number of cells in each place of the blob includes a nearst neighbor
```


## 4. Problem
#### * [미로탈출 14923](https://www.acpcmicpc.net/problem/14923)

#### * Reference code

------