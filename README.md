# Algorithm

- 알고리즘 문제를 풀어보고 모범 코드와 비교합니다

### 사용언어

- Java, Kotlin

### 이용 사이트

- 백준, 프로그래머스

---

### 백트래킹 알고리즘

모든 경우의 수를 전부 고려하는 알고리즘. 상태공간을 트리로 나타낼 수 있을 때 적합한 방식이다.

1. **DFS**

- 최대한 깊이 내려간 뒤, 더이상 깊이 갈 곳이 없을 경우 옆으로 이동

- [43165](https://github.com/kimjjunho/Algorithm/blob/main/Kotlin/Programmers/Level2/43165.md) 

- [44639105](https://github.com/kimjjunho/Algorithm/blob/main/Java/Baekjoon/44639105%20드래그백.md)

2. **BFS**

- 최대한 넓게 이동한 다음, 더 이상 갈 수 없을 때 아래로 이동




### 탐욕법(Greedy)

나중을 생각하지 않고 순간마다 최선의 선택을 하는 알고리즘이다.

- [42883](https://github.com/kimjjunho/Algorithm/blob/main/Kotlin/Programmers/Level2/42883.md)



### Stack

한 쪽 끝에서만 자료를 넣고 뺄 수 있는 LIFO (후입선출) 형식의 자료 구조

**연산**

- pop() : 스택에서 가장 위에 있는 항목을 제거한다
- push(item) : item 하나를 스택의 가장 윗 부분에 추가한다
- peek() : 스택의 가장 위에 있는 항목을 반환한다
- isEmpty() : 스택이 비어 있을 때에 true를 반환한다

**예제** 

- [64061](https://github.com/kimjjunho/Algorithm/blob/main/Kotlin/Programmers/Level1/64061.md)
- [12909](https://github.com/kimjjunho/Algorithm/tree/main/Java/Programmers/Level2)

