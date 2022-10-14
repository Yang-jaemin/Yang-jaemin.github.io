---
title : "[Programmers Lv1] 행렬의 덧셈"
categories :
    - Algorithm
tag :
    - Algorithm
toc: true
toc_sticky : true
comments : true
sidebar_main: true
---

## 문제



<img src="../../images/plus_matrix.png" alt="plus_matrix" style="zoom:50%;" />



처음으로 lv.1에서 이차원 리스트를 다루는 문제입니다. 

어려울 건 없고 그냥 같은 행,열을 더해주고 반환하면 되는 문제 입니다.

## 코드

```python
def solution(arr1, arr2):
    answer = arr1
    for i in range(len(arr1)):
        for j in range(len(arr1[i])):
            answer[i][j] = arr1[i][j] + arr2[i][j]
    return answer
```

이중 포문을 사용해서 풀어나갔습니다.

처음에는 arr1의 길이만큼 for문을 돌렸습니다. (행)

두번째 for문에서는 arr1[i]만큼 돌렸습니다.(열)

그 뒤에 행렬 계산을 해주면 arr1과 arr2가 더해져서 answer에 들어가게 됩니다.

다른 분들은 어떻게 했는지 코드를 보도록 하겠습니다.

```python
def sumMatrix(A,B):
    answer = [[c + d for c, d in zip(a, b)] for a, b in zip(A,B)]
    return answer
```

가장 좋아요가 많이 달린 풀이 입니다.

처음 배열 A,B를 행을 a,b에 나누고

c,d에 열을 나눠서 계산해줬습니다.

아직 저에겐 보기 힘든 코드입니다..ㅜㅜ

## 얻어가는 것

### 2차원 리스트

여기서 말하려는 2차원 리스트는 흔히 생각하는 N x 2 행렬입니다.

위의 문제에서 2차원 리스트 출력을 구현해 봤는데 다른 방법도 있나 알아보시죠.

#### 2차원 리스트 출력

1. for문 한 번 쓰기

   ```python
   >>> a = [[10, 20], [30, 40], [50, 60]]
   >>> for x, y in a:    # 리스트의 가로 한 줄(안쪽 리스트)에서 요소 두 개를 꺼냄
   ...     print(x, y)
   ...
   10 20
   30 40
   50 60
   ```

2. for문 두 번 쓰기

   ```python
   a = [[10, 20], [30, 40], [50, 60]]
   
   for i in a:        # a에서 안쪽 리스트를 꺼냄
       for j in i:    # 안쪽 리스트에서 요소를 하나씩 꺼냄
           print(j, end=' ')
       print()
   ```

3. range 사용하기

   ```python
   a = [[10, 20], [30, 40], [50, 60]]
   
   for i in range(len(a)):            # 세로 크기
       for j in range(len(a[i])):     # 가로 크기 a[i] [값, 값]의 len은 2
           print(a[i][j], end=' ')
       print()
   ```

4. while문 한 번 쓰기

   ```python
   a = [[10, 20], [30, 40], [50, 60]]
   
   i = 0
   while i < len(a):    # 반복할 때 리스트의 크기 활용(세로 크기)
       x, y = a[i]      # 요소 두 개를 한꺼번에 가져오기
       print(x, y)
       i += 1           # 인덱스를 1 증가시킴
   ```

5. while문 두 번 쓰기

   ```python
   a = [[10, 20], [30, 40], [50, 60]]
   
   i = 0
   while i < len(a):           # 세로 크기
       j = 0
       while j < len(a[i]):    # 가로 크기
           print(a[i][j], end=' ')
           j += 1              # 가로 인덱스를 1 증가시킴
       print()
       i += 1                  # 세로 인덱스를 1 증가시킴
   ```

방법들이 꽤 다양해서 그때 그때 생각나는 것을 사용하면 될 것 같습니다.
