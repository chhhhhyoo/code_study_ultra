### 개념 문제

1. **BFS(너비 우선 탐색)** 알고리즘의 작동 원리를 설명하고, 어떤 자료구조를 사용하는지, 그리고 그 이유는 무엇인지 설명해주세요.

**Breadth-First Search(BFS)** is a fundamental graph traversal algorithm that explores all nodes at the current depth level before moving on to nodes in the next depth level.

The BFS algorithm proceeds as follows :
    1) Initialize a queue and insert the starting node.
    2) Mark the starting node as visited to avoid revisiting.
    3) While the queue is not empty:
        a) Dequeue a node N from the front of the queue.
        b) If N is the target, the search terminates.
        c) Else, enqueue all unvisited neighbors of N and mark them as visited.
    4) Repeat until queue is empty or the target is found.

BFS uses a queue(First-In-First-Out). This ensures that nodes are explored in the exact order they are discovered.
Because of the queue's FIFO nature, BFS will guarantee that all nodes at a particular depth are visited before any nodes at the next depth level are visited.

2. **BFS와 DFS(깊이 우선 탐색)**의 차이점은 무엇이며, 각각 어떤 종류의 문제에 더 적합한지 예시를 들어 설명해주세요.




3. **BFS 알고리즘의 시간 복잡도는 O(V+E)**인데, 그래프의 형태(예: 밀집 그래프 vs 희소 그래프)가 실제 수행 시간에 어떤 영향을 미칠 수 있을지 설명해주세요.
