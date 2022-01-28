# Codingtest
## [문제] 미로 탈출
+ 입력 조건 : 첫째 줄에 두 정수 N, M (4<=N, M <= 200)이 주어집니다. 다음 N개의 줄에는 각각 M개의 정수(0 혹은 1)로 미로의 정보가 주어집니다. 
각각의 수들은 공백 없이 붙어서 입력으로 제시됩니다. 
또한 시작 칸과 마지막 칸은 항상 1입니다.
+ 출력조건 : 첫째 줄에 최소 이동 칸의 개수를 출력합니다.


### 미로 탈출 : 문제 해결 아이디어
+ BFS는 시작 지점에서 가까운 노드부터 차례대로 그래프의 모든 노드를 탐색합니다.
+ 상, 하, 좌, 우로 연결된 모든 노드로의 거리가 1로 동일합니다.
++ 따라서 (1, 1) 지점부터 BFS를 수행하여 모든 노드의 최단 거리 값을 기록하면 해결할 수있습니다.
+ 예시로 다음과 같이 3 X 3 크기의 미로가 있다고 가정합시다.


### 미로 탈출 : 답안 예시 (Python)

```python
# BFS 소스코드 구현
def bfs(x, y):
# 큐(Queue) 구현을 위해 deque 라이브러리 사용
queue = deque()
queue.append((x, y))
# 큐가 빌 때까지 반복하기
while queue:
x, y = queue.popleft()
# 현재 위치에서 4가지 방향으로의 위치 확인
for i in range(4):
nx = x + dx[i]
ny = y + dy[i]
# 미로 찾기 공간을 벗어난 경우 무시
if nx < 0 or nx >= n or ny < 0 or ny >= m:
continue
# 벽인 경우 무시
if graph[nx][ny] == 0:
continue
# 해당 노드를 처음 방문하는 경우에만 최단 거리 기록
if graph[nx][ny] == 1:
graph[nx][ny] = graph[x][y] + 1
queue.apped((nx, ny))
# 가장 오른쪽 아래까지의 최단 거리 반환
return graph[n -1][m - 1]

from collections import deque
# N, M을 공백을 기준으로 구분하여 입력 받기
# 2차원 리스트의 맵 정보 입력 받기
graph = []
for i in range(n):
graph.append(list(map(int, input())))

# 이동할 네 가지 방향 정의 (상, 하, 좌, 우)
dx = [-1, 1, 0, 0]
dy = [0, 0, -1, 1]

# BFS를 수행한 결과 출력 
print(bfs(0, 0))
```
