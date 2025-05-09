## 개념 문제

### 1. N×N 크기의 2차원 정수 행렬을 시계 방향으로 90도 회전시키는 기능을 구현한다고 가정해 봅시다. 각 행렬의 원소가 회전 후 어떤 새로운 위치로 이동해야 할지에 대한 좌표 변환 규칙 아이디어를 시뮬레이션하여 설명해주세요. 예를 들어, 원래 행렬의 (r,c) 위치에 있던 원소는 회전 후 어떤 (r',c') 위치로 이동해야 할까요? 이 규칙을 일반화하여 설명하고, 이를 구현하기 위한 주요 단계를 논리적으로 나열해주세요.

**문제 이해**
- 입력 : 정사각형 행렬 N x N
- 목표 : 모든 원소를 90도 시계방향으로 회전한 새로운 위치로 옮기는 규칙 찾기

**작은 시뮬레이션**
```
행렬(2x2)

(0,0)	(0,1)

(1,0)	(1,1)

위치변화

(0,0) → (0,1)

(0,1) → (1,1)

(1,0) → (0,0)

(1,1) → (1,0)
```

**변화 규칙 분석**
- 기존 col값 -> r'
- N - 1 - 기존 row값 -> c'

  => (r, c) → (c, N-1-r)

**구현 논리**

Note that we need to **create a new array**, go through each element and move, and return the new array.

1. 입력 행렬 크기 N을 구한다
2. N x N 크기의 빈 행렬을 만든다.
3. 모든 (r,c)에 대해, (c, N-1-r) 위치에 원래 (r,c) 값을 저장한다.
4. 새 행렬을 반환한다.


### 2. 2차원 평면 상에서 현재 위치 (x,y)에서 시작하여 '동', '서', '남', '북' 방향으로 특정 거리만큼 이동하는 명령들을 처리하는 기능을 구현한다고 가정해 봅시다. 각 이동 명령이 주어졌을 때, 현재 좌표를 어떻게 갱신해야 할지에 대한 좌표 갱신 아이디어를 시뮬레이션하여 설명해주세요. 여러 개의 이동 명령이 순차적으로 주어졌을 때, 최종 도착 좌표를 계산하기 위한 논리적인 처리 흐름을 설명하고, 이를 구현하기 위한 핵심적인 변수 관리 방안에 대한 아이디어를 제시해주세요.

**문제 이해**
- 방향에 따른 적절한 (x,y) 업데이트
- 이동거리는 다를 수 있음
- 이동 누적(이전 위치 기준 이동)

**작은 시뮬레이션**
```
초기위치 (0,0)

'동'으로 3칸 이동

'북'으로 2칸 이동

'서'로 1칸 이동

'남'으로 4칸 이동

위치변화

'동' 3칸 → (0, 0) → (3, 0)
(x가 +3 증가)

'북' 2칸 → (3, 0) → (3, 2)
(y가 +2 증가)

'서' 1칸 → (3, 2) → (2, 2)
(x가 -1 감소)

'남' 4칸 → (2, 2) → (2, -2) - 최종 위치
(y가 -4 감소)
```

**변화 규칙 분석**

'동': x += 거리

'서': x -= 거리

'남': y -= 거리

'북': y += 거리

**구현 논리**

1. x, y를 초기화
2. for 명령어 in 명령어 리스트:
     - 방향에 맞게 x, y를 업데이트(위의 규칙 참고)
3. 최종 x, y 출력
