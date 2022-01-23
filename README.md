# 코딩테스트
## DFS/BFS 

### 스택 자료구조
+ 먼저 들어 온 데이터가 나중에 나가는 형식(선입후출)의 자료구조입니다.
+ 입구와 출구가 동일한 형태로 스택을 시각화 할 수 있습니다.
+ 스택 동작 예시
+ 삽입(5)-삽입(2)-삽입(3)-삽입(7)-삭제()-삽입(1)-삽입(4)-삭제
### 스택 구현 예제 (Python)
```python
stack = []
# 삽입(5)-삽입(2)-삽입(3)-삽입(7)-삭제()-삽입(1)-삽입(4)-삭제
stack.append(5)
stack.append(2)
stack.append(3)
stack.append(7)
stack.pop()
stack.append(1)
stack.append(4)
stack.pop()

print(stack[::-1]) # 최상단 원소부터 출력
print(stack) # 최하단 원소부터 출력

실행결과
[1, 3, 2, 5]
[5, 2, 3, 1]
```

### 재귀함수
+ 재귀함수(Recursive Function)란 자기 자신을 다시 호출하는 함수를 의미합니다.
+ 단순한 형태의 재귀 함수 예제
+ + '재귀 함수를 호출합니다.'라는 문자열을 무한히 출력합니다.
+ + 어느 정도 출력하다가 최대 재귀 깊이 초과 메세지가 출력됩니다.
```python

def recursive_function():
print('재귀 함수를 호출합니다.')
recursive_function()

recursive_function()
```

### 재귀 함수의 종료 조건
+ 재귀 함수를 문제 풀이에서 사용할 때는 재귀 함수의 종료 조건을 반드시 명시해야 합니다.
+ 종료 조건을 제대로 명시하지 않으면 함수가 무한히 호출 될 수 있습니다.
+ + **종료 조건**을 포함한 재귀 함수 예제
```python
def recursive_function(i):
# 100번째 호출을 했을 때 종료되도록 종료 조건 명시
if i == 100:
return
print(i, '번째 재귀함수에서', i + 1, '번째 재귀함수를 호출합니다.')
recursive_function(i+1)
print(i, '번째 재귀함수를 종료합니다.')

recursive_function(1)
```

